# منو Hysteria2
---
<p align="center">
در این منو شما امکان مدیریت کاربران رو دارید.
<br>

<img src="/docs/Picture/hysteria2menu.png">
</p>

### توضیحات منو


<h4>
1. گزینه یک مربوط به نصب هسته و راه اندازی است که در مرحله نصب انجامش دادیم و دیگر نیازی به نصب دوباره نیست.
</h4>

----

<h4>
2. افزودن کاربر (Add User)
</h4>

- پس از انتخاب گزینه `2` از شما نام کاربری رو میخواد که با حروف و اعداد میتونید وارد کنید
از کارکتر های غیراز حروف انگلیسی و اعداد استفاده نکنید.
- در مرحله بعد مقدار ترافیک کاربر رو با اعداد و بر اساس گیگبایت وارد کنید
- در مرحله سوم مقدار روز برای انقضا کاربر را با اعداد انتخاب کنید به طور مثال `30` روز که معادل یک ماه میباشد
```
Enter the username: return
Enter the traffic limit (in GB): 30
Enter the expiration days: 30
User return added successfully.
```
---

<h4>
3. ویرایش کاربر (Edit User)
</h4>

- پس از انتخاب گزینه `3` از شما نام کاربری میخواد 
- انتخاب نام کاربر جدید
- انتخاب ترافیک جدید
- انتخاب مقدار روز انقضا جدید
- بروزرسانی پسورد جدید 
- بروزرسانی تاریخ ایجاد کاربر
- مسدود کردن کاربر


```
Enter the username you want to edit: return
Enter the new username (leave empty to keep the current username):
Enter the new traffic limit (in GB) (leave empty to keep the current limit):
Enter the new expiration days (leave empty to keep the current expiration days):
Do you want to generate a new password? (y/n): n
Do you want to generate a new creation date? (y/n): n
Do you want to block the user? (y/n): n
```

<h5>
نکته : 
</h5>

- مواردی که `leave empty to keep the current` دارن میتوانید بدون دادن مقادیر بزارید تا مقدار قبلی بدون تغییر باقی بماند
- مواردی که `(y/n)` دارن میتونید با زدن `n` بعنوان مخفف `no` رد بشید و مقادیر بدون تغییر بزارید
- در صورت تغییر نام کاربری و پسورد نیاز هستش که دوباره به کاربر اشتراک بدید و اشتراک قبلی کاربر قطع خواهد شد

---

<h4>
4. ریست کاربر (Reset User)
</h4>

بعد از انتخاب گزینه ریست کاربر مقدار نام کاربری را وارد کنید سپس کاربر ریست میشود
این گزینه درصورتی استفاده میشود که کاربر روز یا حجمش به اتمام رسیده و میخواد دوباره همان مقدار قبلی کاربر بروزرسانی کنید تا دوباره متصل شود.

---

<h4>
5. حذف کاربر (Remove User)
</h4>

بعد از انتخاب گزینه حذف کاربر نام کاربری کاربر مورد نظر وارد نمایید تا حذف شود.

---

<h4>
6. نمایش کاربر (Get User)
</h4>

بعد از انتخاب گزینه نمایش کاربر نام کاربری وارد کنید و اطلاعات کاربر به صورت زیر میتونید دریافت کنید.

```
Enter the username: return
User Details:
Username:         return
Password:         eeDQW4ZwvqFBgZZjIqNUrgHY8za3Lc99
Total Traffic:    30.00 GB
Total Usage:      0 GB
Time Expiration:  2025-02-13 (0/30 Days)
Blocked:          false
Status:           Offline
```

---

<h4>
7. لیست کاربران (List Users)
</h4>

بعد از انتخاب گزینه لیست کاربران به شما لیست کل کاربران نمایش  داده میشود :

```
Username             Traffic Limit (GB)   Expiration (Days) Creation Date        Password                       Blocked
jeff                 50                   120             2025-01-14           WWRDnembtjaooTJJXkBizOkY9fmyLzgE false
return               30                   30              2025-01-14           eeDQW4ZwvqFBgZZjIqNUrgHY8za3Lc99 false
hys2                 50                   30              2024-12-10           qAuwQ3b9kVsjoCHi9DtslWjtq9JMUbj4 true
```

---

<h4>
8. نمایش ترافیک(Check Traffic Status)
</h4>

بعد از انتخاب گزینه نمایش ترافیک مصرف دانلود و آپلود هر کاربر به صورت زیر نمایش داده میشود :

```
Traffic Data:
-------------------------------------------------
User            Upload (TX)     Download (RX)   Status
-------------------------------------------------
jeff            392.00MB        9.45GB          Online
-------------------------------------------------
return          554.52MB        19.19GB         Online
-------------------------------------------------
hys2            4.82GB          143.71GB        Offline
-------------------------------------------------

```

---

<h4>
9. نمایش کانفیگ (Show User URI)
</h4>

بعد از انتخاب نمایش کانفیگ از شما مقدار نام کاربری میخواد که بعد از وارد کردن 
 `IPv4` و `IPv6` کانفیگ و `qrcode` کانفیگ هارو نمایش میدهد.

نکته : 
- درصورت فعال بودن ساب لینک ها در انتها مقدار ساب لینک کاربر را هم نمایش خواهد داد.

