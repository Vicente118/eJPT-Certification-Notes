
Let's take a target ip : 10.10.135.33

```bash
nmap -sC 10.10.135.33 (Perform default scripts scans)
nmap --script=mongodb-info 10.10.135.33
nmap --script=<SCRIPTNAME> 10.10.135.33
```