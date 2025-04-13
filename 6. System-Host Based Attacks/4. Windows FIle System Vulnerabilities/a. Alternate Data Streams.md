
- Alternate Data Streams (ADS) is a NTFS file attribute and was designed to provide compatibility with the MacOS HFS (Hierarchy File System).
- Any file created on a NTFS formatted drive will have two streams:
	1. Data Stream: Default stream that contains data of the file.
	2. Resoluce Stream: Typically conatins the metadata of the file.

- We can use ADS to hide malicious code or executables in the file attribute resource stream (metadata) of a legitimate file.

[DEMO]

- Create a textfile: notepad test.txt:secret.txt
- Write whatever you want in it. The fiile is saved as test.txt and when we open it it doesnt show what we wrote in it. Because we actually wrote in the hidden file.

Hide a payload:
```PowerShell
> type payload.exe > text.txt:secret.exe
> del payload.exe (Del the payload)
> start text.txt:secret.exe

> mklink wupdate.exe /path/to/text.txt:secret.exe (Symlink if needed due to access denied)
> wupdate 

It executes the hidden payload
```