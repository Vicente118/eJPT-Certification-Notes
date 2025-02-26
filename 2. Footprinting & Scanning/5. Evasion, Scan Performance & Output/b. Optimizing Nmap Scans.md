Let's take a target ip : 10.10.135.33

```bash
nmap -T<0-5> 10.10.135.33 (See 1.Active.b for explaination)

nmap --host-timeout 5s 10.10.135.0/24 (Skip hosts after 5 seconds)

nmap --scan-delay 5s 10.10.135.33 (5s between each packets being sent = can be useful to be stealh on the network)
```