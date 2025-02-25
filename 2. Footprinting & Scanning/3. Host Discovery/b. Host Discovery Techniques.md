
Crucial phase to identify live hosts on a network before further exploration and vulnerability assessment.

Ping Sweep : Sending ICMP Echo Requests (ping) to a range of IP addresses to identify hosts.

ARP Scanning : Using Address Resolution Protocol (ARP) requests to identify hosts on a local network. ARP scanning is effective in discovering hosts within the same broadcast domain.

TCP SYN Ping (Half-Open Scan) : Sending TCP SYN packets to a specific port to check if a host is alive. If the host is alive, it responds within a TCP SYN-ACK. This technique is stealthier than ICMP ping.

UDP Ping : Sending UDP packets to a specific port to check if a host is alive.

TCP ACK Ping: Sending TCP ACK packets to a specif port to check if a host is alive.

SYN-ACK Ping : Sending TCP SYN-ACK packets to a specific port check if a host is alive.