Ping Sweep : Sending ICMP Echo Requests (ping) to a range of IP addresses to identify hosts.

ICMP Echo request:
- Type : 8
- Code : 0

ICMP Echo Reply:
- Type : 0
- Code : 0

```bash
ping www.domain.com
ping 10.10.128.33
ping -c 5 10.10.128.33  (5 ICMP Echo Requests)
fping -a -g 10.10.128.0/24 2>/dev/null (Ping the whole subnet to see which hosts is alive and redirecting the errors the /dev/null)
```

