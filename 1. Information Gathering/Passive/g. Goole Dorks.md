
GOOGLE HACKING DATASE: https://www.exploit-db.com/google-hacking-database              => Great ressource to find some sensitive information

Imaginary target : ine.com

Limit result to 1 domain :
```
site:ine.com
```

Looking for an admin or forum panel in url : 
```
site:ine.com inurl:admin
site:ine.com inurl:forum
```

Enumerate subdomains :
```
site:*.ine.com
site:*.ine.com intitle:admin
```

Find files :
```
site:*.ine.com filetype:pdf
```

Looking for a keyword:
```
site:ine.com <keyword>
```

Site with directory listing enabled:
```
intitle:index of
```

Finding an older version of a website (Using waybackmachine is probably better):
```
cache:ine.com
```

Finding maybe passwords :
```
inurl:auth_user_file.txt
inurl:passwd.txt
```

