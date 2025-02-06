Packets : Streams of bits running as electric signals on physical media used for data transmission. 

Packet structure :

| HEADER  |
| ------- |
| PAYLOAD |
Header  : Ensure that host can correctly interpret the payload
Payload : The actual information that's being sent

---
The OSI Model : Conceptual framework that standarizes the functions of a telecommunication  or computer sysem into seven layers


| #   | OSI LAYER          | FUNCTION                                                                                                                                                                        | EXEMPLES                    |
| --- | ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------- |
| 7   | APPLICATION LAYER  | Provides network services directly to end-users or applications                                                                                                                 | HTTP, FTP, IRC, DNS,...     |
| 6   | PRESENTATION LAYER | Translates data between the application and lowers layers. Responsible for data format translation, encryption and compression to ensure data is presented in a readable format | SSL/TLS, JPEG, GIF,...      |
| 5   | SESSION LAYER      | Manages sessions or connections between applications. Handles synchonization, dialog control and token management.                                                              | APIs, NETBIOS, RPC,...      |
| 4   | TRANSPORT LAYER    | Ensures end-to-end communication and provides flow control                                                                                                                      | TCP, UDP                    |
| 3   | NETWORK LAYER      | Responsible for logical addressing and routing (Logical addressing)                                                                                                             | IP, ICMP, IPSec,...         |
| 2   | DATA LINK LAYER    | Manges access to the physical medium and provides error detection. Responsible for framing, addressing and erro checking of data frames                                         | Ethernet, PPP, Switches,... |
| 1   | PHYSICAL LAYER     | Deals with the physical connection between device                                                                                                                               | USB, Ethernet Cables, ...   |
