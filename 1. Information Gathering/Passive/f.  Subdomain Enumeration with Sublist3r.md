Sublist3r is not an active subdomains tool like ffuf or gobuster ! It's stays passive by founding all it's informations by OSINT.



```bash
sudo apt-get install sublist3r
sublist3r.py -d <domain> -v -p 433 -t 20
```

-d  : domain name
-e  : search engines (If not specified, it will use all search engines by default)
-p  : ports
-t   : threads
-v  : verbose