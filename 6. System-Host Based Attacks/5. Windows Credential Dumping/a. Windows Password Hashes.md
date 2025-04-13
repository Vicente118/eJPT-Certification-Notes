- The Windows OS stores hashed user account passwords locally in the SAM database. Authentication and verification is facilitaded by the Local Security Authority. Windows uses NTLM hash since Vista.

- SAM (Security Account Manager) is a database file that is responsible for managing user accounts and passwords on Windows. This file is protected by the kernel but it exists method to dump SAM hashes from the LSASS process. In modern versions od Windows, the SAM database is encrypted with syskey.

- Need elevate privileges to dump hashes.

--------------------------------------

- LM (LanMan) is the default hashing algorithm for old versions of Windows.
- Password is broken into seven character chunks. All characters are then converted into uppercase. Each chunk is then hashed separatly with DES algorithm.
- Can easily be cracked.

---------

- NTLM is a collection of authentification protocols that are utilized in Windows to facilitate authentication between computers. The authentication process involves using a valid username and password to authenticate successfully.
- More secure than LM. Uses MD4 algorithm to hash a full password.