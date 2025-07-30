# آیپی‌های مورد اعتماد و بات‌های معروف
جمع‌آوری فهرست آی‌پی‌های هر بات بصورت جداگانه از هم - گوگل‌بات - کلودفلر - بینگ - یاندکس - تلگرام - توییتر و ... .

همه فهرست‌ها بر اساس [CIDR-Notation](https://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing) ایجاد شده‌‎اند و می‌توانید از این فهرست‌ها در فایروال سرور استفاده کنید.

 فایل [all.ips](all.ips) در پوشه [iplists/](iplists/) فهرستی از تمامی آی‌پی‌ها به شما خواهد داد.

همه فهرست‌ها بصورت دوره‌ای و زمانبندی شده در گیت‌هاب بروزرسانی می‌شوند.
<!-- TODO: Better Readme -->
  
```
.
├── all.ips 
│   Combined List of all IP addresses found in iplists/
│
└── iplists/
    │
    ├── ahrefsbot.ips
    │   IP-Addresses used by the AhrefsBot Crawler
    │   
    ├── applebot.ips
    │   IP-Addesses used by the Apple Crawler
    │   
    ├── betteruptimebot.ips
    │   IP-Addesses used by the BetterUptime Bot
    │   
    ├── bingbot.ips
    │   IP-Addesses used by the Bing Crawler
    │   
    ├── bunnycdn.ips
    │   IP-Addesses used by the bunny.net CDN
    │   
    ├── cloudflare.ips
    │   IP-Addesses used by the Cloudflare CDN
    │   
    ├── duckduckbot.ips
    │   IP-Addesses used by the DuckDuckGo Crawler
    │   
    ├── facebookbot.ips
    │   IP-Addesses used by the Facebook Link-Preview Bot
    │   
    ├── fastly.ips
    │   IP-Addesses used by the Fastly CDN
    │   
    ├── freshpingbot.ips
    │   IP-Addesses used by the Freshping Bot
    │   
    ├── googlebot.ips
    │   IP-Addesses used by the Google Crawler
    │   
    ├── imagekit.ips
    │   IP-Addesses used by the Imagekit.io Image Proxy
    │   
    ├── imgix.ips
    │   IP-Addesses used by the Imgix Image Proxy
    │   
    ├── internal.ips
    │   Internal IP-Addresses
    │   
    ├── marginalia.ips
    │   IP-Addresses used by the Marginalia Search Crawler
    │   
    ├── mojeekbot.ips
    │   IP-Addesses used by the Mojeek Crawler
    │   
    ├── molliewebhook.ips
    │   IP-Addesses used by Mollie to send out Webhooks
    │   
    ├── outageowl.ips
    │   IP-Addesses used by the Outage Owl Bot
    │   
    ├── pingdombot.ips
    │   IP-Addesses used by the Pingdom Bot
    │   
    ├── rssapi.ips
    │   IP-Addesses used by the RSSAPI.net Feed parser
    │   
    ├── quiccloud.ips
    │   IP-Addesses used by the Quic.cloud
    |
    ├── stripewebhook.ips
    │   IP-Addesses used by Stripe to send out Webhooks
    │   
    ├── telegrambot.ips
    │   IP-Addesses used by the Telegram Link-Preview Bot
    │   
    ├── twitterbot.ips
    │   IP-Addesses used by the Twitter/X Link-Preview Bot
    │
    ├── uptimerobot.ips
    │   IP-Addesses used by UptimeRobot.com
    │
    ├── webpagetestbot.ips
    │   IP-Addesses used by Webpagetest.org
    │
    └── yandex.ips 
        IP-Addesses used by the Yandex Crawler
        
```

بعنوان مثال؛ برای استفاده این فهرست آیپی‌ها در CSF و سرورهای ALMALINUX که از cPanel استفاده می‌کنند می‌توانید فایل /etc/cron.d/csf_update را ویرایش کنید.
```
nano /etc/cron.d/csf_update
```
یا
```
vi /etc/cron.d/csf_update
```

شما می‌توانید با اضافه کردن دستورات زیر در CRONJOB سیستم عامل خود و هر روز ساعت 30 دقیقه بامداد آخرین بروزرسانی را در سرور خود دریافت کنید:
```
30 0 * * * root rm -f /etc/csf/googlebot.allow && wget -O /etc/csf/googlebot.allow https://raw.githubusercontent.com/MahdiAhazan/IPList/refs/heads/main/iplists/googlebot.ips > /dev/null 2>&1
30 0 * * * root rm -f /etc/csf/yandexbot.allow && wget -O /etc/csf/yandexbot.allow https://raw.githubusercontent.com/MahdiAhazan/IPList/refs/heads/main/iplists/yandex.ips > /dev/null 2>&1
30 0 * * * root rm -f /etc/csf/twitterbot.allow && wget -O /etc/csf/twitterbot.allow https://raw.githubusercontent.com/MahdiAhazan/IPList/refs/heads/main/iplists/twitterbot.ips > /dev/null 2>&1
30 0 * * * root rm -f /etc/csf/uptimerobot.allow && wget -O /etc/csf/uptimerobot.allow https://raw.githubusercontent.com/MahdiAhazan/IPList/refs/heads/main/iplists/uptimerobot.ips > /dev/null 2>&1
30 0 * * * root rm -f /etc/csf/telegrambot.allow && wget -O /etc/csf/telegrambot.allow https://raw.githubusercontent.com/MahdiAhazan/IPList/refs/heads/main/iplists/telegrambot.ips > /dev/null 2>&1
30 0 * * * root rm -f /etc/csf/bingbot.allow && wget -O /etc/csf/bingbot.allow https://raw.githubusercontent.com/MahdiAhazan/IPList/refs/heads/main/iplists/bingbot.ips > /dev/null 2>&1
30 0 * * * root rm -f /etc/csf/ahrefsbot.allow && wget -O /etc/csf/ahrefsbot.allow https://raw.githubusercontent.com/MahdiAhazan/IPList/refs/heads/main/iplists/ahrefsbot.ips > /dev/null 2>&1
30 0 * * * root rm -f /etc/csf/pingdombot.allow && wget -O /etc/csf/pingdombot.allow https://raw.githubusercontent.com/MahdiAhazan/IPList/refs/heads/main/iplists/pingdombot.ips > /dev/null 2>&1
30 0 * * * root rm -f /etc/csf/bunnycdn.allow && wget -O /etc/csf/bunnycdn.allow https://raw.githubusercontent.com/MahdiAhazan/IPList/refs/heads/main/iplists/bunnycdn.ips > /dev/null 2>&1
30 0 * * * root rm -f /etc/csf/cloudflare.allow && wget -O /etc/csf/cloudflare.allow https://raw.githubusercontent.com/MahdiAhazan/IPList/refs/heads/main/iplists/cloudflare.ips > /dev/null 2>&1
30 0 * * * root rm -f /etc/csf/quiccloud.allow && wget -O /etc/csf/quiccloud.allow https://raw.githubusercontent.com/MahdiAhazan/IPList/refs/heads/main/iplists/quiccloud.ips > /dev/null 2>&1
```

یا همه لیست‌ها را با:
```
30 0 * * * root rm -f /etc/csf/allbot.allow && wget -O /etc/csf/allbot.allow https://raw.githubusercontent.com/MahdiAhazan/IPList/refs/heads/main/all.ips > /dev/null 2>&1
```

سرویس کرانجاب رو ریستارت کنید:
```
systemctl restart crond.service
```
حالا وقت آن است که فهرست‌ها را در فایل /etc/csf/csf.allow اضافه کنید:
```
nano /etc/csf/csf.allow
```
یا
```
vi /etc/csf/csf.allow
```

خطوط زیر را در فایل اضافه کنید.
```
# https://github.com/MahdiAhazan/IPList
# GOOGLEBOT|86400|0|https://raw.githubusercontent.com/MahdiAhazan/IPList/refs/heads/main/iplists/googlebot.ips
include /etc/csf/google.allow
# YANDEXBOT|86400|0|https://raw.githubusercontent.com/MahdiAhazan/IPList/refs/heads/main/iplists/yandex.ips
include /etc/csf/yandex.allow
# TWITTERBOT|86400|0|https://raw.githubusercontent.com/MahdiAhazan/IPList/refs/heads/main/iplists/twitterbot.ips
include /etc/csf/twitterbot.allow
# UPTIIMEROBOTBOT|86400|0|https://raw.githubusercontent.com/MahdiAhazan/IPList/refs/heads/main/iplists/uptimerobot.ips
include /etc/csf/uptimerobot.allow
# TELEGRAMBOT|86400|0|https://raw.githubusercontent.com/MahdiAhazan/IPList/refs/heads/main/iplists/telegrambot.ips
include /etc/csf/telegrambot.allow
# BINGBOT|86400|0|https://raw.githubusercontent.com/MahdiAhazan/IPList/refs/heads/main/iplists/bingbot.ips
include /etc/csf/bingbot.allow
# AHREFBOT|86400|0|https://raw.githubusercontent.com/MahdiAhazan/IPList/refs/heads/main/iplists/ahrefsbot.ips
include /etc/csf/ahrefsbot.allow
# PINGDOMBOT|86400|0|https://raw.githubusercontent.com/MahdiAhazan/IPList/refs/heads/main/iplists/pingdombot.ips
include /etc/csf/pingdombot.allow
# BUNNYCDN|86400|0|https://raw.githubusercontent.com/MahdiAhazan/IPList/refs/heads/main/iplists/bunnycdn.ips
include /etc/csf/bunnycdn.allow
# CloudFlare|86400|0|https://raw.githubusercontent.com/MahdiAhazan/IPList/refs/heads/main/iplists/cloudflare.ips
include /etc/csf/cloudflare.allow
# QUICCLOUD|86400|0|https://raw.githubusercontent.com/MahdiAhazan/IPList/refs/heads/main/iplists/quiccloud.ips
include /etc/csf/quiccloud.allow
```
یا

```
# https://github.com/MahdiAhazan/IPList
# ALLBOT|86400|0|https://raw.githubusercontent.com/MahdiAhazan/IPList/refs/heads/main/all.ips
include /etc/csf/allbot.allow
```

ریستارت کردن سرویس csf هم فراموش نکنید باید انجام بشه در انتها
```
csf -r
```
