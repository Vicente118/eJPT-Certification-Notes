The goal here is to make a ping scan with Nmap on the whole network in order to find IP addresses that answers to us. 

---

First step is to find your IP and the range IP of the network
```bash
ip a s
ifconfig
```

Output : 192.168.2.190/24

--- 

Nmap scan:
```bash
sudo nmap -sn 192.168.2.0/24
```
-sn : no port scan = ping scan (ICMP requests)

--- 
Netdiscover tool:
```bash
sudo netdiscover -i wlan0 -r 192.168.2.0/24
```

