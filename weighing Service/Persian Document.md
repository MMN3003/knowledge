# مستندات کلاس SettingService

این کلاس در پروژه‌ی **WeighingService** وظیفه مدیریت تنظیمات (Settings) را بر عهده دارد. تنظیمات به صورت JSON ذخیره شده و از طریق این کلاس بارگذاری، ویرایش و ذخیره می‌شوند.

## فهرست محتوا

- [پکیج‌های مورد استفاده](#پکیج‌های-مورد-استفاده)
- [متدها](#متدها)
  - [سازنده SettingService](#سازنده-settingservice)
  - [AddListener](#متد-addlistener)
  - [Get](#متد-get)
  - [Set](#متد-set)
  - [Dispatch](#متد-dispatch)
  - [Store](#متد-store)

## پکیج‌های مورد استفاده

در این کلاس از پکیج‌ها و کتابخانه‌های زیر استفاده شده است:

- `Newtonsoft.Json`: برای سریالیزه و دی‌سریالیزه کردن JSON
- `System.IO`: برای عملیات خواندن و نوشتن فایل
- `System.Collections.Generic`: برای استفاده از لیست‌ها
- `System.Linq`: برای کار با مجموعه‌ها
- `System`: برای استفاده از توابع عمومی سیستم
- `WeighingService.Utilities`: شامل ابزارهای کمکی پروژه

## متدها

### سازنده SettingService

```csharp
public SettingService()
```

این متد سازنده هنگام ایجاد نمونه‌ای از کلاس `SettingService` اجرا می‌شود. در این متد، فایل `Config.json` که در پوشه `Assets` قرار دارد، بارگذاری شده و تنظیمات به عنوان یک آبجکت `Models.Setting` ذخیره می‌شود.

### متد AddListener

```csharp
public void AddListener(Action handler)
```

این متد به شما امکان می‌دهد تا یک شنونده (Listener) به لیست شنونده‌ها اضافه کنید. شنونده‌ها می‌توانند به تغییرات تنظیمات واکنش نشان دهند.

### متد Get

```csharp
public Models.Setting Get()
```

این متد تنظیمات فعلی را برمی‌گرداند. از این متد برای دسترسی به تنظیمات فعلی استفاده می‌شود.

### متد Set

```csharp
public void Set(Models.Setting settings)
```

این متد برای تنظیم و ذخیره‌ی تنظیمات جدید استفاده می‌شود. پس از ذخیره‌سازی تنظیمات جدید، شنونده‌های اضافه شده نیز فراخوانی می‌شوند.

### متد Dispatch

```csharp
private void Dispatch(List<Action> handlersCopy)
```

این متد تمامی شنونده‌های اضافه شده را فراخوانی می‌کند تا از تغییرات جدید تنظیمات آگاه شوند. اگر در هنگام اجرای هر شنونده خطایی رخ دهد، خطا لاگ می‌شود.

### متد Store

```csharp
private void Store()
```

این متد تنظیمات جدید را به صورت JSON در فایل `Config.json` ذخیره می‌کند. اگر در حین ذخیره‌سازی خطایی رخ دهد، خطا لاگ می‌شود.

# مستندات کلاس WebService

کلاس **WebService** در پروژه‌ی **WeighingService** به عنوان یک سرور وب محلی عمل می‌کند که از طریق API با سایر قسمت‌های سیستم ارتباط برقرار می‌کند. این کلاس از `HttpSelfHostServer` برای اجرای یک سرور خودمیزبان (Self-hosted) استفاده می‌کند.

## فهرست محتوا

- [پکیج‌های مورد استفاده](#پکیج‌های-مورد-استفاده)
- [متدها](#متدها)
  - [Init](#متد-init)
  - [Start](#متد-start)
  - [SetAll](#متد-setall)
  - [SettingListener](#متد-settinglistener)
  - [Restart](#متد-restart)
  - [Stop](#متد-stop)
- [کلاس RequestResponseLoggingHandler](#کلاس-requestresponselogginghandler)

## پکیج‌های مورد استفاده

در این کلاس از پکیج‌ها و کتابخانه‌های زیر استفاده شده است:

- `System.Net.Http`: برای مدیریت درخواست‌ها و پاسخ‌ها HTTP
- `System.Threading.Tasks`: برای انجام عملیات ناهمگام (Asynchronous)
- `System.Web.Http`: برای ایجاد کنترلرهای API
- `System.Web.Http.SelfHost`: برای راه‌اندازی سرور خودمیزبان
- `WeighingService.Models`: شامل مدل‌های داده پروژه
- `WeighingService.Utilities`: شامل ابزارهای کمکی پروژه

## متدها

### متد Init

```csharp
public void Init()
```

این متد، سرور وب را با بارگذاری تنظیمات فعلی و اعمال آن‌ها آماده‌سازی می‌کند. همچنین یک شنونده برای تنظیمات اضافه می‌کند که در صورت تغییر تنظیمات، به‌روزرسانی‌های لازم انجام شود.

### متد Start

```csharp
public void Start()
```

این متد، سرور وب را راه‌اندازی می‌کند و تنظیمات مربوط به مسیریابی (Routing) و مدیریت درخواست‌ها را انجام می‌دهد. همچنین درخواست‌ها و پاسخ‌ها را لاگ می‌کند.

### متد SetAll

```csharp
private void SetAll(Setting settings)
```

این متد تنظیمات مورد نیاز سرور وب مانند پورت را از شیء `Setting` گرفته و آن‌ها را اعمال می‌کند.

### متد SettingListener

```csharp
private void SettingListener()
```

این متد به تغییرات تنظیمات واکنش نشان می‌دهد. اگر پورت تغییر کرده باشد، سرور وب را مجدداً راه‌اندازی می‌کند.

### متد Restart

```csharp
public void Restart()
```

این متد سرور وب را ابتدا متوقف کرده و سپس دوباره راه‌اندازی می‌کند.

### متد Stop

```csharp
public void Stop()
```

این متد سرور وب را متوقف کرده و منابع مورد استفاده را آزاد می‌کند.

## کلاس RequestResponseLoggingHandler

```csharp
public class RequestResponseLoggingHandler : DelegatingHandler
```

این کلاس یک هندلر سفارشی برای لاگ کردن جزئیات درخواست‌ها و پاسخ‌ها در سرور وب است. هندلر لاگ‌های مربوط به هر درخواست و پاسخ را ثبت می‌کند.

### متد SendAsync

```csharp
protected override async Task<HttpResponseMessage> SendAsync(HttpRequestMessage request, CancellationToken cancellationToken)
```

این متد به صورت ناهمگام جزئیات هر درخواست و پاسخ HTTP را لاگ می‌کند. ابتدا جزئیات درخواست و سپس جزئیات پاسخ را پس از پردازش ثبت می‌کند.


# مستندات کلاس WeightService

کلاس **WeightService** در پروژه‌ی **WeighingService** مسئول مدیریت و دریافت داده‌های وزن از دستگاه وزن‌کشی است. این کلاس اطلاعات وزنی را که از دستگاه دریافت می‌شود، پردازش کرده و بر اساس زمان آخرین به‌روزرسانی، آن‌ها را بازمی‌گرداند.

## فهرست محتوا

- [پکیج‌های مورد استفاده](#پکیج‌های-مورد-استفاده)
- [متدها](#متدها)
  - [سازنده WeightService](#سازنده-weightservice)
  - [SetAll](#متد-setall)
  - [SettingListener](#متد-settinglistener)
  - [set](#متد-set)
  - [Get](#متد-get)

## پکیج‌های مورد استفاده

در این کلاس از پکیج‌ها و کتابخانه‌های زیر استفاده شده است:

- `System`: برای استفاده از انواع پایه و کلاس‌های اصلی سیستم.
- `System.Collections.Generic`: برای استفاده از انواع عمومی لیست‌ها و مجموعه‌ها.
- `System.Linq`: برای انجام عملیات مرتبط با کوئری و مدیریت داده‌ها.
- `System.Text`: برای استفاده از عملیات مرتبط با رشته‌ها.
- `System.Threading.Tasks`: برای مدیریت عملیات ناهمگام.

## متدها

### سازنده WeightService

```csharp
public WeightService()
```

این متد سازنده، کلاس `WeightService` را مقداردهی می‌کند. در ابتدا، تنظیمات سیستم از طریق `SettingService` بارگذاری می‌شود و شنونده‌ای برای تغییرات تنظیمات اضافه می‌شود. سپس، یک نمونه از `WeighingService` گرفته شده و یک شنونده برای دریافت داده‌های وزن اضافه می‌شود.

### متد SetAll

```csharp
private void SetAll(Models.Setting settings)
```

این متد تنظیمات مرتبط با مدت زمان معتبر ماندن داده‌های وزن را از شیء `Setting` گرفته و اعمال می‌کند. مقدار `secondsLast` تعیین می‌کند که داده‌های وزنی تا چند ثانیه بعد از آخرین به‌روزرسانی معتبر باشند.

### متد SettingListener

```csharp
private void SettingListener()
```

این متد به تغییرات تنظیمات واکنش نشان می‌دهد و در صورت تغییر، تنظیمات جدید را اعمال می‌کند.

### متد set

```csharp
public void set(string stringWeight)
```

این متد داده وزنی که از دستگاه وزن‌کشی دریافت شده است را پردازش می‌کند. اگر مقدار دریافت شده معتبر باشد، آن را به عنوان وزن فعلی ذخیره می‌کند و زمان آخرین به‌روزرسانی را ثبت می‌کند.

### متد Get

```csharp
public (float?, string) Get()
```

این متد، وزن فعلی را برمی‌گرداند. اگر از زمان آخرین به‌روزرسانی بیشتر از مقدار `secondsLast` گذشته باشد، به جای وزن، `null` و یک پیام خطا برگردانده می‌شود. اگر داده معتبر باشد، وزن و پیام خطا `null` برمی‌گردد.

Here is the Persian documentation for the `SettingController.cs` file in Markdown format:

```markdown
# مستندات کلاس SettingController

کلاس **SettingController** در پروژه‌ی **WeighingService** مسئول مدیریت تنظیمات سیستم از طریق API است. این کلاس به کاربران امکان می‌دهد تا تنظیمات جاری را مشاهده و به‌روزرسانی کنند.

## فهرست محتوا

- [پکیج‌های مورد استفاده](#پکیج‌های-مورد-استفاده)
- [متدها](#متدها)
  - [سازنده SettingController](#سازنده-settingcontroller)
  - [Current](#متد-current)
  - [Fetch](#متد-fetch)
  - [Update](#متد-update)

## پکیج‌های مورد استفاده

در این کلاس از پکیج‌ها و کتابخانه‌های زیر استفاده شده است:

- `System`: برای استفاده از انواع پایه و کلاس‌های اصلی سیستم.
- `System.Collections.Generic`: برای استفاده از انواع عمومی لیست‌ها و مجموعه‌ها.
- `System.IO`: برای انجام عملیات ورودی و خروجی روی فایل‌ها.
- `System.Linq`: برای انجام عملیات مرتبط با کوئری و مدیریت داده‌ها.
- `System.Net`: برای استفاده از انواع مرتبط با شبکه و پروتکل‌های HTTP.
- `System.Net.Http`: برای مدیریت درخواست‌ها و پاسخ‌های HTTP.
- `System.Threading.Tasks`: برای مدیریت عملیات ناهمگام.
- `System.Web.Http`: برای ساخت APIهای مبتنی بر HTTP.
- `WeighingService.Constants`: برای استفاده از ثابت‌ها و مقادیر تعریف‌شده در پروژه.
- `WeighingService.Models`: برای مدیریت مدل‌های داده‌ای مرتبط با تنظیمات.
- `WeighingService.Services`: برای استفاده از سرویس‌های موجود در پروژه.

## متدها

### سازنده SettingController

```csharp
public SettingController()
```

این متد سازنده، کلاس `SettingController` را مقداردهی می‌کند. در این متد، نمونه‌هایی از `SettingService` و `WeighingService` بارگذاری می‌شود که برای مدیریت تنظیمات و تعامل با سرویس‌های وزن‌کشی استفاده می‌شوند.

### متد Current

```csharp
[HttpGet]
public IHttpActionResult Current()
```

این متد مسئول ارسال محتوای یک فایل HTML به عنوان پاسخ HTTP است. فایل HTML مربوط به تنظیمات در مسیر `Assets/Setting.html` قرار دارد. اگر فایل به درستی خوانده شود، محتوای HTML با کد وضعیت 200 (OK) بازگردانده می‌شود. در صورت بروز خطا در خواندن فایل، یک خطای داخلی سرور (Internal Server Error) برگردانده می‌شود.

### متد Fetch

```csharp
[HttpGet]
public IHttpActionResult Fetch()
```

این متد تنظیمات فعلی سیستم را از `SettingService` دریافت کرده و به عنوان پاسخ HTTP بازمی‌گرداند. این پاسخ شامل شیء `Setting` در قالب یک شیء `Response` است که حاوی کد خطا و پیام خطا نیز می‌باشد.

### متد Update

```csharp
[HttpPut]
public IHttpActionResult Update(Setting updatedSetting)
```

این متد برای به‌روزرسانی تنظیمات سیستم استفاده می‌شود. تنظیمات جدید که از طریق پارامتر `updatedSetting` دریافت می‌شوند، توسط `SettingService` ذخیره می‌شوند. در صورت موفقیت‌آمیز بودن عملیات، تنظیمات جدید به همراه کد وضعیت 200 (OK) بازگردانده می‌شود. در صورت بروز خطا، یک پیام خطا با کد خطای داخلی سرور برگردانده می‌شود.
```

این مستندات به شما کمک می‌کند تا با عملکرد کلاس `SettingController` و نحوه‌ی کارکرد آن در پروژه‌ی `WeighingService` آشنا شوید.