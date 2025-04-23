Let's take a target ip :  10.10.135.33

```bash
nmap -sA 10.10.135.33 (SYN ACK Scan, good to see if there is filtered ports AND conclude if there is a firewall)

nmap -f 10.10.135.33 (Fragments the packets)
nmap -f 10.10.135.33 --mtu 8 (Fragments the packets with an offset of minimum 8 bytes per packets)

nmap -D RND:10 10.10.135.33 (Decoy with multiples IP, evades firewall and IDS)
```