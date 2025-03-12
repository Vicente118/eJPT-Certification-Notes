
\- MySQL is an open-source relational database management system based on SQL.
\- MySQL utilizes TCP port 3306 by default.


Let's take a target ip : 10.10.10.10

```bash
Interesting modules :

- auxiliary/scanner/mysql/mysql_version
- auxiliary/scanner/mysql/mysql_login
- auxiliary/admin/mysql/mysql_enum
- auxiliary/admin/mysql/mysql_sql
- auxiliary/scanner/mysql/mysql_file_enum
- auxiliary/scanner/mysql/mysql_hashdump
- auxiliary/scanner/mysql/mysql_schemadump
- auxiliary/scanner/mysql/mysql_writable_dirs
```