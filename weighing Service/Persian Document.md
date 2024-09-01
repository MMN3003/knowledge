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


این مستندات به شما کمک می‌کند تا با عملکرد کلاس `SettingService` در پروژه‌ی `WeighingService` آشنا شوید.

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

این مستندات به شما کمک می‌کند تا با عملکرد کلاس `WebService` و نحوه‌ی کارکرد آن در پروژه‌ی `WeighingService` آشنا شوید.


