- Windows access tokens are a core element of the authentification process on Windows and are created and managed by the Local Security Authority Subsystem Service (LSASS)

 - Can be compared to a web cookie. Useful to avoid putting credentials each time we need higher privilege.

- See privilege in meterpreter with getprivs command.
	1. *SeAssignPrimaryToken*: This allows a user to impersonate a token.
	2. *SeCreateToken*: This allows a user to create an arbitrary token with administrative privileges.
	3. *SeImpersonatePrivilege*: This allow a user to create a process under the security context of another user typically with administrative privileges.

- Incognito is a built-in meterpreter module that allows us to impersonate user tokens.

```PowerShell
Meterpreter:

> load incognito
> list_tokens -u
> impersonate_token <"TOKEN">
> migrate to explorer.exe
```
