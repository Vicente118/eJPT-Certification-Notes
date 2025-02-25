
Target domain : target.ine.local

```bash
nmap -sC -sV -p- -T4 -O target.ine.local

Open ports :
- ftp
- ssh
- smtp
- http
- imap
- ssl/imap
- mysql
- mysqlx?
```

HTTP Server leaks FLAG1 : 
`92aadd1973ed4a32a06e3d8c93198eee`

We can connect as anonymous user on FTP service and we find the FLAG3 : `b1802cc8511e43d7b4b437b44e3372a7`

We also find a SQL credentials :
`db_admin:password@123`

target.ine.local/robots.txt leaks the /secret-info/flag.txt file that contains the second flag. FLAG2 :
`5bfc36d000d64f3fb7e6c71c686fd39c`

Connect to the MySQL database :
```bash
mysql -u db_admin -p -h target.ine.local 
show databases

+----------------------------------------+
| Database                               |
+----------------------------------------+
| FLAG4_cbefca236714432e8eb6b5bb7a686ba7 |
| information_schema                     |
| mysql                                  |
| performance_schema                     |
| sys                                    |
+----------------------------------------+

```

FLAG4 : 
`cbefca236714432e8eb6b5bb7a686ba7`

