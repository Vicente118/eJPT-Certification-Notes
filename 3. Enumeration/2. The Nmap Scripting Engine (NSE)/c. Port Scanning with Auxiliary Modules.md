
- Auxiliary modules are used to perform functionality like scanning, discovery and fuzzing.

Let's take a target ip : 10.10.10.22

```bash
sudo service postgresql start

msfconsole

msf6 > db_status

msf6 > workspace -a port_scan

msf6 > search portscan

msf6 > use auxiliary/scanner/portscan/tcp

msf6 > show options

msf6 > set RHOSTS 10.10.10.22

msf6 > run
```