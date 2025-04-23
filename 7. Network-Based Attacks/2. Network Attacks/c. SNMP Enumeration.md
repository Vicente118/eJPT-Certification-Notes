- SNMP (Simple Network Management Protocol) is a widely used protocol for monitoring and managing networked devices, such as routers, switches, printers, servers and more.
- It allows network administrators to query devices for status information, configure certain settings and receive alerts or traps when specifics events occur.
- SNMP is an application layer protocol that typically uses UDP for transport. It involves three primary components:
	- SNMP Manager: Responsible for querying and interacting with SNMP agents or networked devices.
	- SNMP Agent: Software running on networked devices that responds to queries and sends traps.
	- Management Information Base (MIB): A hierarchical database that defines the structure of data available through SNMP. Each piece of data has a unique Object identifier (OID).
- Port 161 (UDP): Used for SNMP queries.
- Port 162 (UDP): Used for SNMP traps.

---

[LAB]

```bash
> nmap -sU -p161 demo.ine.local
Port 161 is open and SNMP is running.

Snmp Brute Force to find community strings:
> nmap -sU -p161 --script=snmp-brute demo.ine.local
PORT    STATE SERVICE
161/udp open  snmp
| snmp-brute: 
|   public - Valid credentials
|   private - Valid credentials
|_  secret - Valid credentials

> nmap -sU -sV demo.ine.local
SNMP Version 1

> nmap -sU -p161 --script snmp-* demo.ine.local > snmp_info
This gives us a large amount of informations. As users for examples.

```