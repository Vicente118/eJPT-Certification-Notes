Let's take a target ip : 10.22.4.56

Windows systems frequently block the pings, so it's useful here to use ***nmap -Pn***

(Lot of repetitions, see previous chapter)

To link our nmap scan with Metasploit :

```bash
nmap -Pn -sC -0 10.22.4.56 -oX output_file
```

(Continued in next page)