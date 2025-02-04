DNS : Protocol that is used to resolve domain names or hosts names to IP addresses

DNS server = nameserver

---

DNS Records : 
```
-  A       => Resolves hostname or domain to an IPv4 address
-  AAAA    => Resolves hostname or domain to an IPv6 address
-  NS      => Reference to the domains nameserver
-  MX      => Resolves a domain to a mail server
-  CNAME   => Used for domain aliases
-  TXT     => Text record
-  HINFO   => Host information
-  SOA     => Domain auditory
-  SRV     => Service records
-  PTR     => Resolves an IP address to a hostname
```

---

DNS Interrogation : Process of enumerating DNS records for a specific domain
```
Goal => Probe a DNS server to provide us important information like the IP address of a domain, subdomain, ...
```

---

/etc/hosts : First domain resolver checked to access an ip address

-------

DNS enum : Active DNS recon tool to identify DNS records
```bash
dnsenum <domain>
```

--- 
Dig : tools that makes the same work as DNS enum but visually better
``` bash
dig axfr @<nameserver> <domain>
```

---
DNS Zone Transfert : Copying or transfering zone files from one DNS server to another

---

DNS brute force
```bash
fierce -dns <domain>
```
