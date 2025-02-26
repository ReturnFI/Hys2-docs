## توضیحات صفحه تنظیمات

<p align="center">
 <img src="https://github.com/user-attachments/assets/d125f1d9-4d79-4685-bc96-0d5a0eba7422" width="700" height="500">
</p>


---

#### لینک های اشتراک Subscriptions 

سربرگ `Subscriptions` شامل دو زیر سربرگ میباشد

- لینک اشتراک `SingBox`

برای فعال سازی لینک اشتراک `SingBox` نیاز به یک دامنه یا ساب دامنه و پورت آزاد روی سرور خود دارید

در کادر `Domain` دامنه یا ساب دامنه خود را وارد نمایید و در بخش `Port` یک پورت آزاد به عدد وارد نمایید سپس چند لحظه صبر کنید تا سرویس های مورد نیاز نصب شوند و پیغام `SingBox started successfully!` دریافت نمایید.

- لینک اشتراک `Normal`

برای فعال سازی لینک اشتراک `Normal` نیاز به یک دامنه یا ساب دامنه و پورت آزاد روی سرور خود دارید

در کادر `Domain` دامنه یا ساب دامنه خود را وارد نمایید و در بخش `Port` یک پورت آزاد به عدد وارد نمایید سپس چند لحظه صبر کنید تا سرویس های مورد نیاز نصب شوند و پیغام `Normal subscription started successfully!` دریافت نمایید.

---

### بات تلگرام Telegram Bot

<p align="center">
 <img src="https://github.com/user-attachments/assets/3895c879-a1b9-4f91-be28-a0a3c202ec76" width="500" height="250">
</p>

- برای فعال سازی بات تلگرام به موارد زیر نیاز دارید:
  - با استفاده از ربات `@BotFather` یک ربات ایجاد کنید و توکن ربات کپی کنید و در کادر `API Token` وارد نمایید.
  - با استفاده از ربات `@userinfobot` آیدی عددی حساب تلگرام خود رو بدست بیارید و در کادر `Admin ID` وارد نمایید.

سپس بر روی دکمه `Start` زده و صبر کنید تا پیغام `Telegram bot started successfully!` دریافت نمایید.

---

### تغییر پورت Port 


<p align="center">
 <img src="https://github.com/user-attachments/assets/9dbcea87-1bf8-4e7f-aa7c-6f1aa2f62c50" width="500" height="250">
</p>

در این بخش میتواند پورت سرویس اصلی `Hysteria2` تغییر دهید.

این پورت مربوط به سرویس اصلی `Hysteria2` میباشد و در صورت تغییر نیاز هست که کاربران کانفیگ خود را بروزرسانی کنند.

---

### تغییر SNI 

<p align="center">
 <img src="https://github.com/user-attachments/assets/d827da74-a8cb-4323-aa42-dfbbb599834b" width="500" height="250">
</p>

با استفاده از این سربرگ شما میتوانید `SNI` خود را که در هنگام نصب انتخاب کرده اید را تغییر دهید.

دقت داشته باشید با تغییر `SNI` مقادیر `pinSHA256` در فایل `config.json` تغییر خواهد کرد و در صورت قطع شدن کاربران باید دوباره کانفیگ دریافت کنن.


---

### تغییر IP


<p align="center">
 <img src="https://github.com/user-attachments/assets/b19f2ca7-23e6-4f9c-b424-1e6c5bc5ce30" width="500" height="250">
</p>


درصورتی که از تانلینگ یا فلوتینگ `IP` استفاده میکنید میتوانید از این سربرگ استفاده کنید و مقادیر `IP` کانفیگ های خود را تغییر دهید.


- کادر `IPv4` تغییر `IP` ورژن `4` کانفیگ ها
- کادر `IPv6` تغییر `IP` ورژن `6` کانفیگ ها
