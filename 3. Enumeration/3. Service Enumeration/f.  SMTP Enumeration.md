\- SMTP (Simple Mail Transfer Protocol) is a communication protocol that is used for the transmission of email.
\- SMTP uses TCP port 25 by default. (Sometimes also on port 465 or 587)

Enum user with : auxiliary/scanner/smtp/smtp_enum in MSF

```bash
domain : openmailbox.xyz
user from : admin
user to : root
domain ip : demo.ine.local
```

sendmail :
```bash
sendemail -f admin@attacker.xyz -t root@openmailbox.xyz -s demo.ine.local -u Fakemail -m "Hi root, a fake from admin" -o tls=no
```
