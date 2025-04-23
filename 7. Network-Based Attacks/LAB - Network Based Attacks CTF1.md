- Analyze the test.pcap file with wireshark

- Flag:
	1. Put this filter: http.response.code == 200 
	2. We can find in packets destination informations :  10.7.10.47 and 80:86:5b:ab:1e:c4
	3. FIlter to get NetBIOS infos is nbns. Hostname: DESKTOP-9PEA63H
	4. Delete filters and Ctrl+f to search. Put string as research and packet bytes then search mystery_file.ps1. The user is rwalters
	5. Packets details + string and search PowerShell. User-Agent: Mozilla/5.0 (Windows NT; Windows NT 10.0; en-US) **WindowsPowerShell**/5.1.19041.3031
	6. Same research with Coinbase. Then right click on request and Follow TCP Stream then find COinbase string and we find the ID. hnfanknocfeofbddgcijnmhnfnkdnaad

