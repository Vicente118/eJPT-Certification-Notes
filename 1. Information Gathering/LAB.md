Website : http://target.ine.local
IP           : 192.253.99.3

---

http://target.ine.local/robots.txt : **FLAG1{0d310dd194aa4f62900e6a99827643c3}**

---

nmap -A target.ine.local              : **FL@G2{7b982f60c76c4497a4124d27cf8fb0e4}**

---
dirb http://target.ine.local => http://target.ine.local/wp-content/uploads/ 
                => flag.txt : **FLAG3{dfea350e32da456db15a8f744c2ab4aa}**

---
Backup file can be found here :  target.ine.local/wp-config.bak
File is then downloaded and we just

```bash
cat ~/Downloads/wp-config.bak
```

And here we can find the flag :  **FLAG4{66e4b434ddd94c589b497e3131ebdb84}**

---

Mirroring file -> HTTrack :

```bash
httrack http://target.ine.local

grep "FLAG5" -R target.ine.local/
```
Flag : **FLAG5{627dcf345e364e4686be8f83d36683fa}**  