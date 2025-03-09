
```bash
nmap -Pn -sC -0 10.22.4.56 -oX output_file

sudo service postgresql start

msfconsole    // Open Metasploit Framework

db_status     // Check database status

workspace -a TEST   // Add a new workspace named TEST

db_import /home/vdarras/output_file  // Import Nmap Scan to the database

/// DATA HAS BEEN LOADED IN DB ///

hosts        // Information about hosts
services     // Information about services
vulns        // Print all vulnerabilities in the database

/// To run the scan inside metasploit directly ///

msf6 > db_nmap -Pn -sV -sC -p- -O localhost
```