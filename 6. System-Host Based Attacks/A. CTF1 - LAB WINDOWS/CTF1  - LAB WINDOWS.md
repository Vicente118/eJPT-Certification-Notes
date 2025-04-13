Two machine :
- target1.ine.local
- target2.ine.local

1. Brute force http target1.ine.local with MSF
2. bob:password_123321
3. Flag1 is in target1.ine.local/webdav/flag1.txt
4. Use davtest to check if we could upload a webshell
5. Use cadaver to actually upload the webshell
6. type C:\flag2.txt to get Flag2
7. Brute force SMB as User administrator : administrator:pineapple
8. To get a shell: impacket-psexec administrator@10.2.31.3
9. type C:\flag3.txt
10. type C:\Users\Administrator\Desktop\flag4.txt
