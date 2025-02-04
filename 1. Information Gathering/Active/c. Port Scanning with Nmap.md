NMAP ARGUMENTS
```bash
None       : SYN scan on the 1000 most used ports
-Pn        : Do not check if the host is online
-p-        : ports 0-6535
-p 80,445  : ports 80 and 445
-p 80-1000 : ports 80-1000
-sU        : UDP Scan
-T0-5      : Timing templates. T3 by default (or nmap choose for you depending your netwok), T0, T1 and T2 are stealthy. T4 and T5 are aggressive. Avoid to fast scan if network is bad.
-sV        : Shows services versions
-O         : Operating system detection (Not 100% reliable)
-v         : Increase verbosity
-sC        : Run a list of default scripts on the services in order to enumerate more informations about the target
-A         : Aggressive scan == -sV -O -sC
-oN <file> : Redirect the output in a choose file
-oX <file.xml> : Redirect the output in the xml format (Can be interesting for metasploit)
```
