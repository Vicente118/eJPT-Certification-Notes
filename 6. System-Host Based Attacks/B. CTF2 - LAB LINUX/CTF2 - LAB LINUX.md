- First server is vulnerable to Shellshock. We can have a reverse shell easily.
- cat /flag.txt : FLAG1_502820640c1343aca29e09312e236e4e
- Then we can just do a command to find the hidden file mentionned in the lab
```bash
grep -r "FLAG"
.flag.txt:FLAG2_99a13893e8074f09b27788ef132df5a7
```

- Second machine is vulnerable to a ssh authentification bypass exploit.
- We get reverse shell then cat /home/user/flag.txt FLAG3_794e0bb8c04349608149abb68458039b
- We can now exploit the welcome SUID binary and get root (Same technique that the course)
- cat /root/flag.txt : FLAG4_97b8999e2aae4635b933535c44fd75e5