نام کد فیلتر: دیتا‌ماینر تابلوخوانی به TSETMC

🔘 انتقال دیتاهای تابلوخوانی به ماتریس [ih] سایت TSETMC برای افزایش بازه زمانی دیتاهای بورسی از 60 به 300 روز.

🔘 جمع‌آوری و ادغام دیتاها از دو API برای ایجاد دیتای جامع.

⚪️ نحوه استفاده
این کد باید ابتدای کدهای دیگر قرار گیرد و به طور خودکار هنگام بارگذاری صفحه اجرا شود.

🟢 نکات و پیشنهادات بهبود
استفاده از XMLHttpRequest ممکن است در برخی شرایط باعث کندی شود. استفاده از fetch می‌تواند عملکرد را بهبود بخشد.
⚪️ به دلیل اطمینان از سازگاری با طیف گسترده‌ای از کاربران و مرورگرهای قدیمی‌تر،‌ از XMLHttpRequest استفاده کردم. برای کاربران حرفه‌ای، تغییر به fetch امکان‌پذیر است، اما نیاز به دانش فنی دارد.

زبان برنامه‌نویسی: JavaScript
برنامه‌نویس: Anonymous
//BourseXtreme
//Anonymous
var totalBuyVolumeHaqiqi = 0;
var totalSellVolumeHaqiqi = 0;
var totalBuyVolumeHoqoqi = 0;
var totalSellVolumeHoqoqi = 0;
for (var i = 0; i < 10; i++)
{
 if ([ih][i].ct.Buy_CountI > 0)
 {
  totalBuyVolumeHaqiqi += [ih][i].ct.Buy_I_Volume;
  totalSellVolumeHaqiqi += [ih][i].ct.Sell_I_Volume;
 }
 if ([ih][i].ct.Buy_CountN > 0)
 {
  totalBuyVolumeHoqoqi += [ih][i].ct.Buy_N_Volume;
  totalSellVolumeHoqoqi += [ih][i].ct.Sell_N_Volume;
 }
}
var powerSaranehHaqiqi = (totalSellVolumeHaqiqi > 0) ? (totalBuyVolumeHaqiqi / totalSellVolumeHaqiqi) : 0;
var powerSaranehHoqoqi = (totalSellVolumeHoqoqi > 0) ? (totalBuyVolumeHoqoqi / totalSellVolumeHoqoqi) : 0;
var powerSaranehHaqiqiToday = ([ih][0].ct.Sell_I_Volume > 0) ? ([ih][0].ct.Buy_I_Volume / [ih][0].ct.Sell_I_Volume) : 0;
var powerSaranehHoqoqiToday = ([ih][0].ct.Sell_N_Volume > 0) ? ([ih][0].ct.Buy_N_Volume / [ih][0].ct.Sell_N_Volume) : 0;
if (powerSaranehHaqiqi > 1)
{
 (cfield0) = "میانگین قدرت خرید حقیقی 10 روز گذشته: <span style='color:green; font-weight:bold'>" + powerSaranehHaqiqi.toFixed(2) + "</span>";
}
else
{
 (cfield0) = "میانگین قدرت خرید حقیقی 10 روز گذشته: <span style='color:red; font-weight:bold'>" + powerSaranehHaqiqi.toFixed(2) + "</span>";
}
if (powerSaranehHoqoqi > 1)
{
 (cfield1) = "میانگین قدرت خرید حقوقی 10 روز گذشته: <span style='color:green; font-weight:bold'>" + powerSaranehHoqoqi.toFixed(2) + "</span>";
}
else
{
 (cfield1) = "میانگین قدرت خرید حقوقی 10 روز گذشته: <span style='color:red; font-weight:bold'>" + powerSaranehHoqoqi.toFixed(2) + "</span>";
}
if (powerSaranehHaqiqiToday > powerSaranehHaqiqi)
{
 (cfield2) = "قدرت خرید امروز حقیقی <span style='color:green; font-weight:bold'>بیشتر</span> از 10 روز گذشته است";
}
else if (powerSaranehHaqiqiToday < powerSaranehHaqiqi)
{
 (cfield2) = "قدرت خرید امروز حقیقی <span style='color:red; font-weight:bold'>کمتر</span> از 10 روز گذشته است";
}
else
{
 (cfield2) = "قدرت خرید امروز حقیقی برابر با 10 روز گذشته است";


 نام کد: tsetmcHistoricalDataFetcher

🔘 دریافت و پردازش دیتاهای تاریخی سهام از سایت TSETMC  
- این کد به شما امکان می‌دهد تا دیتاهای قیمتی و حجمی سهام را بدون محدودیت 60 روزه از سایت TSETMC دریافت کنید و به هر تعداد روز دلخواه دسترسی داشته باشید.

🟢 ویژگی‌های کلیدی:
- دریافت داده‌های تاریخی سهام برای تعداد روزهای انتخابی
- اصلاح و تعدیل خودکار تاریخچه دیتاها
- ذخیره‌سازی داده‌ها در ساختار ماتریسی [ih] برای دسترسی ساده‌تر سایر کدها به تاریخچه سهام

⚪️ توسعه:
ساختار انعطاف‌پذیر کد، این امکان را به شما می‌دهد که بر اساس نیازهای خود، از APIهای مختلف استفاده کرده و کد را توسعه دهید.

مثال نحوه استفاده:
if ((l18) === "فولاد")
{
 (cfield0) = [ih][1000].PDrCotVal; // آخرین قیمت 1000 روز پیش
}

زبان برنامه‌نویسی: JavaScript
برنامه‌نویس: Anonymous

@BourseXtreme

لطفا در صورت استفاده یا به اشتراک‌گذاری این کد، با رعایت اصول اخلاق حرفه‌ای، نام کانال و امضای من (Anonymous) را حذف نکنید و از همه مهم‌تر دعا فراموش نشه ❤️

نام کد: BourseXtreme Analyzer Bot v12.3

🔘 تحلیل همه‌جانبه اطلاعات بنیادی، تکنیکال، تابلوخوانی و شاخص‌های کلیدی نماد

🔘 بکارگیری API ضد فیلتر اختصاصی کانال جهت ارسال به تلگرام بدون نیاز به فیلترشکن

🟢 ویژگی‌های کلیدی:
- ارائه اطلاعات جامع از شاخص‌های اصلی نماد
- تحلیل دقیق رفتار معاملاتی حقیقی و حقوقی
- محاسبه و نمایش انواع اندیکاتور و اسیلاتورهای تکنیکال
- تحلیل پرایس اکشن و الگوهای کندل استیک
- ارزیابی جریان نقدینگی و قدرت خرید و فروش
- امتیازدهی به وضعیت کلی نماد از جنبه‌های مختلف

⚪️ کاربرد و توسعه:
این کد با ارائه تحلیل‌های جامع و دقیق، به شما امکان می‌دهد دیدگاهی عمیق‌تر نسبت به وضعیت نمادها کسب کرده و تصمیمات معاملاتی آگاهانه‌تری اتخاذ کنید. علاوه بر این، قابلیت توسعه‌پذیری کد به شما اجازه می‌دهد تا بر اساس معیارها و شروط اختصاصی خود، گزارش‌های تحلیلی را به تلگرام ارسال کنید.

زبان برنامه‌نویسی: JavaScript
برنامه‌نویس: Anonymous

@BourseXtreme

لطفا در صورت استفاده یا به اشتراک‌گذاری این کد، با رعایت اصول اخلاق حرفه‌ای، نام کانال و امضای من (Anonymous) را حذف نکنید و از همه مهم‌تر دعا فراموش نشه ❤️


}

@BourseXtreme
