Let's take a target ip : 10.10.135.33

```bash
nmap -sV 10.10.135.33 (Versions of services running on each ports)
nmap -sV --version-intensity 8 10.10.135.33

nmap -O 10.10.135.33 (Try to detect the Operating System but not so much reliable so be careful)
nmap -O --osscan-guess 10.10.135.33
```