
````markdown
درخواست شما دو بخش دارد:

1. تبدیل جریان کاری که به زبان ساده توضیح دادم به یک **دیاگرام معماری بصری**.
2. ترجمه همان جریان به یک **سند فنی دقیق** برای توسعه‌دهندگان، با ذکر جزئیات پیاده‌سازی.

بیایید هر دو را با همان دقت و جزئیات انجام دهیم.

---

### **بخش ۱: دیاگرام معماری شماتیک (فلوچارت)**

این دیاگرام، کل فرآیند سواپ بین زنجیره‌ای با نقدینگی داخلی را به صورت بصری نمایش می‌دهد.

```mermaid
sequenceDiagram
participant App as 📱 اپلیکیشن اندروید
participant Backend as 🤖 بک‌اند (Go)
participant Phoenix_S as SC Sepolia
participant Phoenix_M as SC Mumbai
participant Treasury_S as 🏦 خزانه‌داری Sepolia
participant Treasury_M as 🏦 خزانه‌داری Mumbai

Note over App, Backend: مرحله ۱: شروع و استعلام قیمت
App->>+Backend: GET /swap/pairs (جفت‌های قابل معامله کدم‌اند؟)
Backend-->>-App: لیست جفت‌ها (بر اساس موجودی خزانه‌داری)

App->>+Backend: POST /swap/quote (۱۰۰ USDT از Sepolia به MATIC)
Backend-->>-App: پاسخ قیمت (۹۸.۵ MATIC به Mumbai با quoteId)

Note over App, Backend: مرحله ۲: تعهد کاربر (آف‌چین)
App->>App: کاربر قیمت را تایید می‌کند
App->>App: ساخت و امضای مجوز Permit برای ۱۰۰ USDT (روی Sepolia)
App->>+Backend: POST /swap/execute (با quoteId و امضای Permit)

Note over Backend, Phoenix_S: مرحله ۳: برداشت دارایی کاربر (روی زنجیره Sepolia)
Backend->>Backend: بررسی سلامت (موجودی کاربر)
Backend->>+Phoenix_S: فراخوانی executeTradeWithPermit(امضا)
Phoenix_S-->>Treasury_S: انتقال ۱۰۰ USDT از کاربر به خزانه‌داری
Phoenix_S-->>-Backend: تراکنش موفق (Tx Hash 1)

Note over Backend, Treasury_M: مرحله ۴: ارسال دارایی به کاربر (روی زنجیره Mumbai)
Backend->>+Treasury_M: ارسال ۹۸.۵ MATIC به آدرس کاربر
Treasury_M-->>-Backend: تراکنش موفق (Tx Hash 2)
Backend-->>-App: پاسخ نهایی (معامله موفق)

Note over App: مرحله ۵: نمایش نتیجه
App->>App: نمایش پیام موفقیت به کاربر
App->>App: (در پس‌زمینه) بررسی موجودی جدید MATIC کاربر
````

---

### **بخش ۲: سند فنی دقیق برای توسعه‌دهندگان**

**موضوع:** پیاده‌سازی MVP ویژگی "سواپ بین زنجیره‌ای با نقدینگی داخلی"

**تکنولوژی‌های کلیدی:** Go (Gin, go-ethereum), Solidity, Kotlin.

#### **۱. زیرساخت و پیکربندی (Backend)**

- **کیف پول‌های خزانه‌داری (Treasury Wallets):**
    
    - ایجاد دو کیف پول مجزا: یکی برای شبکه تستی Sepolia و دیگری برای Mumbai.
        
    - کلیدهای خصوصی باید به صورت امن ذخیره و در بک‌اند در دسترس باشند.
        
- **قرارداد هوشمند `PhoenixContract`:**
    
    - قرارداد باید روی هر دو شبکه مستقر شود و آدرس خزانه‌داری در constructor تنظیم گردد.
        
    - آدرس کیف پول ادمین باید به عنوان `owner` یا `relayer` تنظیم شود.
        

#### **۲. API Endpoints (Backend)**

- **`GET /swap/pairs`**
    
    - لیست جفت‌ارزهای قابل معامله بر اساس موجودی خزانه‌داری.
        
    - برای جفت `USDT_SEPOLIA -> MATIC_MUMBAI`، موجودی MATIC در خزانه‌داری Mumbai باید کافی باشد.
        
- **`POST /swap/quote`**
    
    - ورودی:
        
        ```json
        { "fromAsset": "USDT", "fromChainId": 11155111, "toAsset": "MATIC", "amount": "100" }
        ```
        
    - منطق:
        
        1. استعلام قیمت MATIC/USDT از API خارجی.
            
        2. تخمین هزینه گس با go-ethereum.
            
        3. تبدیل هزینه گس به USDT.
            
        4. محاسبه کارمزد شرکت (مثلاً ۰.۵٪).
            
        5. محاسبه مقدار نهایی دریافتی کاربر.
            
        6. ایجاد و ذخیره `quoteId` با انقضای کوتاه.
            
- **`POST /swap/execute`**
    
    - ورودی:
        
        ```json
        { "quoteId": "...", "userSignature": "0x...", "destinationAddress": "0x..." }
        ```
        
    - منطق:
        
        1. بررسی اعتبار `quoteId`.
            
        2. بررسی balance و allowance کاربر با eth_call.
            
        3. ساخت و ارسال تراکنش برداشت در Sepolia.
            
        4. ساخت و ارسال تراکنش ارسال در Mumbai.
            
        5. ثبت هش تراکنش‌ها و ارسال پاسخ موفق.
            

#### **۳. منطق کلاینت (اندروید)**

- **ماژول `:core`**
    
    - کلاس `PermitSigner` برای ایجاد و امضای Permit (EIP-712).
        
- **ماژول `:data`**
    
    - اینترفیس‌های `SwapRepository` برای `/pairs`, `/quote`, `/execute`.
        
- **ماژول `:feature_swap` (ViewModel & UI)**
    
    - `SwapViewModel`:
        
        1. فراخوانی `getSwapPairs()` برای پر کردن UI.
            
        2. فراخوانی `getQuote()` پس از ورود مقدار.
            
        3. فراخوانی `getNonce` از شبکه Sepolia.
            
        4. ایجاد امضا با `PermitSigner`.
            
        5. اجرای `executeSwap()` با امضا.
            
        6. مدیریت وضعیت‌های UI (Loading, Success, Error).
            

