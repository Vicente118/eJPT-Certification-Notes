
Let's take a target ip : 10.10.128.33

-sn : No port scan
-v : Increase verbosity

```
nmap -sn 10.10.128.34-40 (Scan all ip addresses between 10.10.128.34 and 10.10.128.40)

nmap -sn -iL file.txt (With file.txt containing all the ip we want to scan)

nmap -sn -PS 10.10.128.34 (TCP SYN Ping)
nmap -sn -PS<MINPORT>-<MAXPORT> 10.10.128.34
nmap -sn -PS<PORT>,<PORT>,<PORT> 10.10.128.34
-sn : No port scan)

nmap -sn -PA 10.10.128.34 (TCP ACK Ping)
nmap -sn -PA<MINPORT>-<MAXPORT> 10.10.128.34
nmap -sn -PA<PORT>,<PORT>,<PORT> 10.10.128.34
-sn : No port scan
```
