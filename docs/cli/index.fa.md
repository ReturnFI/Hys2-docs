# راهنمای مدیریت Hysteria2 از طریق رابط خط فرمان (CLI)

این سند یک راهنمای جامع برای استفاده از اسکریپت `cli.py` ارائه می‌دهد، که یک رابط خط فرمان برای مدیریت Hysteria2 و سرویس‌های مرتبط است. این راهنما نصب، مدیریت کاربران، پیکربندی‌های پیشرفته و عیب‌یابی را پوشش می‌دهد. دستورات برای وضوح بیشتر در بخش‌های جداگانه سازماندهی شده‌اند. هر دستور با گزینه‌ها، آرگومان‌ها و رفتار مورد انتظار آن توضیح داده شده است.

## مدیریت Hysteria2

این بخش دستورات مربوط به نصب، به‌روزرسانی و پیکربندی هسته سرویس Hysteria2 را پوشش می‌دهد.

---

### install-hysteria2

Hysteria2 را نصب و پیکربندی می‌کند.

```bash
./cli.py install-hysteria2 --port <port> --sni <sni>
```

*   **`--port` / `-p` (الزامی):** شماره پورتی که Hysteria2 به آن گوش می‌دهد. باید یک عدد صحیح باشد.
*   **`--sni` / `-s` (اختیاری):**  مشخصه نام سرور (SNI) برای استفاده.  پیش‌فرض `bts.com` است.

**مثال:**

```bash
./cli.py install-hysteria2 -p 443 -s example.com
```

---

### uninstall-hysteria2

Hysteria2 را حذف نصب می‌کند.

```bash
./cli.py uninstall-hysteria2
```

---

### update-hysteria2

هسته Hysteria2 را به آخرین نسخه به‌روزرسانی می‌کند.

```bash
./cli.py update-hysteria2
```

---

### restart-hysteria2

سرویس Hysteria2 را مجدداً راه‌اندازی می‌کند.

```bash
./cli.py restart-hysteria2
```

---

### change-hysteria2-port

پورتی که Hysteria2 به آن گوش می‌دهد را تغییر می‌دهد.

```bash
./cli.py change-hysteria2-port --port <new_port>
```

*   **`--port` / `-p` (الزامی):** شماره پورت جدید.

**مثال:**

```bash
./cli.py change-hysteria2-port -p 8080
```

---

### change-hysteria2-sni

SNI مورد استفاده Hysteria2 را تغییر می‌دهد.

```bash
./cli.py change-hysteria2-sni --sni <new_sni>
```

*   **`--sni` / `-s` (الزامی):**  SNI جدید.

**مثال:**

```bash
./cli.py change-hysteria2-sni -s mynew.sni.com
```

---

### backup-hysteria
از پیکربندی فعلی Hysteria2 پشتیبان تهیه می‌کند.
```bash
./cli.py backup-hysteria
```
یک فایل zip حاوی فایل‌های پیکربندی شما در دایرکتوری `/etc/hysteria/` ایجاد می‌کند.

---

### restore-hysteria2
پیکربندی Hysteria2 را از یک فایل پشتیبان ZIP بازیابی می‌کند.
```bash
./cli.py restore-hysteria2 <backup_file_path>
```
*  `backup_file_path`: مسیر فایل ZIP حاوی پشتیبان. این مسیر باید به یک فایل *موجود* اشاره کند. نمی‌تواند یک دایرکتوری باشد. باید قابل خواندن باشد.
**مثال:**
```bash
./cli.py restore-hysteria2 /path/to/backup.zip
```

---

## مدیریت کاربر

این بخش دستورات مربوط به مدیریت کاربران Hysteria2 را شرح می‌دهد.



### list-users

لیست تمام کاربران Hysteria2 پیکربندی شده را نمایش می‌دهد.

```bash
./cli.py list-users
```
خروجی در فرمت JSON خواهد بود.

---

### get-user

اطلاعات دقیق در مورد یک کاربر خاص را بازیابی می‌کند.

```bash
./cli.py get-user --username <username>
```

*   **`--username` / `-u` (الزامی):** نام کاربری کاربری که می‌خواهید اطلاعاتش را دریافت کنید.

**مثال:**

```bash
./cli.py get-user -u testuser
```
خروجی در فرمت JSON خواهد بود.

---

### add-user

یک کاربر جدید Hysteria2 اضافه می‌کند.

```bash
./cli.py add-user --username <username> --traffic-limit <traffic_limit_gb> --expiration-days <expiration_days> --password <password> --creation-date <date>
```

*   **`--username` / `-u` (الزامی):** نام کاربری برای کاربر جدید.
*   **`--traffic-limit` / `-t` (الزامی):**  محدودیت ترافیک برای کاربر، بر حسب گیگابایت (GB).
*   **`--expiration-days` / `-e` (الزامی):**  تعداد روزهایی که حساب کاربری منقضی می‌شود.
*   **`--password` / `-p` (اختیاری):**  رمز عبور برای کاربر.
*   **`--creation-date` / `-c` (اختیاری):**  تاریخ ایجاد حساب در فرمت `YYYY-MM-DD`.

**مثال:**

```bash
./cli.py add-user -u newuser -t 100 -e 30 -p mysecretpassword -c 2023-12-25
```

---

### edit-user

تنظیمات یک کاربر Hysteria2 موجود را ویرایش می‌کند.

```bash
./cli.py edit-user --username <username> --new-username <new_username> --new-traffic-limit <new_traffic_limit_gb> --new-expiration-days <new_expiration_days> --renew-password --renew-creation-date --blocked
```

*   **`--username` / `-u` (الزامی):** نام کاربری کاربری که می‌خواهید ویرایش کنید.
*   **`--new-username` / `-nu` (اختیاری):** نام کاربری جدید برای کاربر.
*   **`--new-traffic-limit` / `-nt` (اختیاری):**  محدودیت ترافیک جدید بر حسب GB.
*   **`--new-expiration-days` / `-ne` (اختیاری):** تعداد جدید روزهای انقضا.
*   **`--renew-password` / `-rp` (اختیاری، پرچم):** اگر اضافه شود، رمز عبور کاربر را تجدید می‌کند.
*   **`--renew-creation-date` / `-rc` (اختیاری، پرچم):** اگر اضافه شود، تاریخ ایجاد کاربر را بازنشانی می‌کند.
*   **`--blocked` / `-b` (اختیاری، پرچم):** اگر اضافه شود، کاربر را مسدود می‌کند.

**مثال (تغییر محدودیت ترافیک و مسدود کردن):**

```bash
./cli.py edit-user -u testuser -nt 50 -b
```

---

### reset-user

آمار ترافیک کاربر را بازنشانی می‌کند.

```bash
./cli.py reset-user --username <username>
```

*    **`--username` / `-u` (الزامی):** نام کاربری برای بازنشانی.

---

### remove-user

یک کاربر Hysteria2 را حذف می‌کند.

```bash
./cli.py remove-user --username <username>
```

*   **`--username` / `-u` (الزامی):** نام کاربری برای حذف.

---

### show-user-uri

URI مربوط به Hysteria2 را برای یک کاربر تولید و نمایش می‌دهد، به صورت اختیاری به عنوان کد QR.

```bash
./cli.py show-user-uri --username <username> --qrcode --ipv <ip_version> --all --singbox --normalsub
```

*   **`--username` / `-u` (الزامی):** نام کاربری که URI برای آن تولید می‌شود.
*   **`--qrcode` / `-qr` (اختیاری، پرچم):** اگر اضافه شود، یک کد QR از URI تولید می‌کند.
*   **`--ipv` / `-ip` (اختیاری):**  نسخه IP (4 یا 6) را برای URI مشخص می‌کند. پیش‌فرض 4 است.
*   **`--all` / `-a` (اختیاری، پرچم):**  URIهای IPv4 و IPv6 را نشان می‌دهد.
*   **`--singbox` / `-s` (اختیاری, پرچم):** اگر سرویس Singbox فعال باشد، لینک اشتراک Singbox را اضافه می‌کند.
*   **`--normalsub` / `-n` (اختیاری، پرچم):** اگر سرویس normalsub فعال باشد، پیوند اشتراک Normal-Sub را شامل می شود.

**مثال (تولید کد QR برای IPv6):**

```bash
./cli.py show-user-uri -u testuser -qr -ip 6
```

---

## مدیریت سرور

این بخش دستورات مربوط به سرور را پوشش می‌دهد.



### traffic-status

آمار استفاده از ترافیک فعلی را نمایش می‌دهد.

```bash
./cli.py traffic-status
```

---

### server-info

اطلاعات سرور را نمایش می‌دهد.

```bash
./cli.py server-info
```
خروجی در فرمت JSON خواهد بود

---

### manage_obfs

تنظیمات مبهم‌سازی (obfs) را در پیکربندی Hysteria2 مدیریت می‌کند.

```bash
./cli.py manage_obfs --remove
./cli.py manage_obfs --generate
```

*   **`--remove` / `-r` (اختیاری، پرچم):**  obfs را از پیکربندی حذف می‌کند.
*   **`--generate` / `-g` (اختیاری، پرچم):**  یک پیکربندی obfs جدید تولید می‌کند.
*   **ناسازگار**: شما باید فقط یکی از `--remove` یا `--generate` را ارائه دهید. ارائه ندادن هیچ کدام خطایی را چاپ می‌کند.

---

### ip-address

آدرس‌های IP سرور ذخیره شده در `.configs.env` را مدیریت می‌کند.

```bash
./cli.py ip-address
./cli.py ip-address --edit --ipv4 <ipv4_address>
./cli.py ip-address --edit --ipv6 <ipv6_address>
```

*   **بدون گزینه:**  آدرس‌های IP شناسایی شده خودکار را به پیکربندی اضافه می‌کند.
*   **`--edit` (اختیاری، پرچم):** ویرایش دستی آدرس‌های IP را فعال می‌کند.
*   **`-4` / `--ipv4` (اختیاری):**  یک آدرس IPv4 جدید را مشخص می‌کند (نیاز به `--edit` دارد).
*   **`-6` / `--ipv6` (اختیاری):**  یک آدرس IPv6 جدید را مشخص می‌کند (نیاز به `--edit` دارد).
    * **با ویرایش** شما *باید* حداقل یکی از `--ipv4` یا `--ipv6` را ارائه دهید.

---

### update-geo

فایل‌های داده GeoIP و GeoSite را به‌روزرسانی می‌کند.

```bash
./cli.py update-geo --country <country>
```

*   **`--country` / `-c` (اختیاری):**  کشوری که فایل‌های Geo برای آن به‌روزرسانی می‌شوند (`iran`، `china`، یا `russia`). پیش‌فرض `iran` است.

**مثال (به‌روزرسانی برای چین):**

```bash
./cli.py update-geo -c china
```

---

### masquerade

تنظیمات masquerade را در پیکربندی Hysteria2 مدیریت می‌کند.

```bash
./cli.py masquerade --remove
./cli.py masquerade --enable <domain>
```

*   **`--remove` / `-r` (اختیاری، پرچم):** پیکربندی masquerade را حذف می‌کند.
*   **`--enable` / `-e` (اختیاری):**  masquerade را با دامنه مشخص شده فعال می‌کند.
* **ناسازگار**: شما باید فقط یکی از `--remove` یا `--enable` را ارائه دهید. ارائه ندادن هیچ کدام خطایی را چاپ می‌کند.

**مثال (فعال کردن masquerade):**

```bash
./cli.py masquerade -e example.com
```

---

## منوی پیشرفته

این بخش دستوراتی را توضیح می‌دهد که عملکردهای اضافی را ارائه می‌دهند.

### install-tcp-brutal

TCP Brutal را نصب می‌کند.

```bash
./cli.py install-tcp-brutal
```

---

### install-warp

WARP را نصب می‌کند.

```bash
./cli.py install-warp
```

---

### uninstall-warp

WARP را حذف نصب می‌کند.

```bash
./cli.py uninstall-warp
```

---

### configure-warp

تنظیمات WARP را پیکربندی می‌کند.

```bash
./cli.py configure-warp --all --popular-sites --domestic-sites --block-adult-sites --warp-option <option> --warp-key <key>
```

*   **`--all` / `-a` (اختیاری، پرچم):** از WARP برای تمام ترافیک استفاده می‌کند.
*   **`--popular-sites` / `-p` (اختیاری، پرچم):** از WARP برای وب‌سایت‌های محبوب استفاده می‌کند.
*   **`--domestic-sites` / `-d` (اختیاری، پرچم):** از WARP برای وب‌سایت‌های داخلی (ایرانی) استفاده می‌کند.
*   **`--block-adult-sites` / `-x` (اختیاری، پرچم):** محتوای بزرگسالان را مسدود می‌کند.
*   **`--warp-option` / `-w` (اختیاری):** بین `warp` (عادی) و `warp plus` انتخاب می‌کند.
*   **`--warp-key` / `-k` (اختیاری):** کلید WARP Plus (اگر `--warp-option` برابر `warp plus` باشد الزامی است).

**مثال (استفاده از WARP Plus):**

```bash
./cli.py configure-warp -w "warp plus" -k YOUR_WARP_PLUS_KEY
```

---

### warp-status

وضعیت فعلی WARP را نمایش می دهد.

```bash
./cli.py warp-status
```
خروجی در فرمت JSON خواهد بود.

---

### telegram

ادغام ربات تلگرام را مدیریت می‌کند.

```bash
./cli.py telegram --action <action> --token <token> --adminid <admin_id>
```

*   **`--action` / `-a` (الزامی):**  عملی که باید انجام شود (`start` یا `stop`).
*   **`--token` / `-t` (برای `start` الزامی است):** توکن ربات تلگرام.
*   **`--adminid` / `-aid` (برای `start` الزامی است):**  شناسه(های) ادمین تلگرام (جدا شده با کاما).

**مثال (راه‌اندازی ربات):**

```bash
./cli.py telegram -a start -t YOUR_BOT_TOKEN -aid 123456789,987654321
```

---

### singbox

سرویس Singbox را مدیریت می‌کند.

```bash
./cli.py singbox --action <action> --domain <domain> --port <port>
```

*   **`--action` / `-a` (الزامی):**  `start` یا `stop`.
*   **`--domain` / `-d` (برای `start` الزامی است):**  نام دامنه برای SSL.
*   **`--port` / `-p` (برای `start` الزامی است):** شماره پورت برای سرویس Singbox.

---

### normal-sub

سرویس Normal-Sub را مدیریت می‌کند.

```bash
./cli.py normal-sub --action <action> --domain <domain> --port <port>
```

*   **`--action` / `-a` (الزامی):** `start` یا `stop`.
*   **`--domain` / `-d` (برای `start` الزامی است):** نام دامنه برای SSL.
*   **`--port` / `-p` (برای `start` الزامی است):** شماره پورت برای سرویس.

---

### webpanel
سرویس وب پنل را مدیریت می‌کند.

```bash
./cli.py webpanel --action <action> --domain <domain> --port <port> --admin-username <admin_username>  --admin-password <admin_password> --expiration-minutes <expiration_minutes> --debug
```

*    **`--action` / `-a` (الزامی):** `start` یا `stop`.
*   **`--domain` / `-d` (برای `start` الزامی است):** نام دامنه برای SSL.
*   **`--port` / `-p` (برای `start` الزامی است):** شماره پورت برای سرویس وب پنل.
*   **`--admin-username` / `-au` (برای `start` الزامی است):** نام کاربری مدیر برای وب پنل.
*   **`--admin-password` / `-ap` (برای `start` الزامی است):** رمز عبور مدیر برای وب پنل.
*   **`--expiration-minutes` / `-e` (اختیاری):** زمان انقضا برای جلسات وب پنل بر حسب دقیقه، پیش فرض: 20.
*   **`--debug` / `-g`** حالت اشکال زدایی وب پنل را فعال می‌کند.
* هنگامی که وب پنل را راه اندازی می‌کنید، اسکریپت وضعیت سرویس‌های مرتبط را نشان می‌دهد.
* وب پنل دارای پورت پیش فرض *80* است.

    ```bash
     ./cli.py webpanel -a start  -d example.com -p 8080 -au admin -ap 1234
    ```

---

### get-webpanel-url
URL وب پنل را دریافت می‌کند.

```bash
./cli.py get-webpanel-url
```

---

### get-webpanel-api-token
توکن API وب پنل را دریافت می‌کند.

```bash
./cli.py get-webpanel-api-token
```

---

### get-webpanel-services-status
وضعیت سرویس‌های وب پنل را دریافت می‌کند.

  ```bash
   ./cli.py get-webpanel-services-status
  ```

---

### get-services-status
وضعیت تمام سرویس‌های مدیریت شده را نمایش می‌دهد (فعال یا غیرفعال).
```bash
./cli.py get-services-status
```

