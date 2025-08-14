Machine ip:10.201.64.83


# Scan of the Windows server;
nmap -sCV -v --min-rate 10000 10.201.64.83
```sh
PORT     STATE SERVICE       VERSION
53/tcp   open  domain        Simple DNS Plus
88/tcp   open  kerberos-sec  Microsoft Windows Kerberos (server time: 2025-08-14 11:46:34Z)
135/tcp  open  msrpc         Microsoft Windows RPC
139/tcp  open  netbios-ssn   Microsoft Windows netbios-ssn
389/tcp  open  ldap          Microsoft Windows Active Directory LDAP (Domain: SOUPEDECODE.LOCAL0., Site: Default-First-Site-Name)
445/tcp  open  microsoft-ds?
464/tcp  open  kpasswd5?
593/tcp  open  ncacn_http    Microsoft Windows RPC over HTTP 1.0
636/tcp  open  tcpwrapped
3268/tcp open  ldap          Microsoft Windows Active Directory LDAP (Domain: SOUPEDECODE.LOCAL0., Site: Default-First-Site-Name)
3269/tcp open  tcpwrapped
3389/tcp open  ms-wbt-server Microsoft Terminal Services
|_ssl-date: 2025-08-14T11:47:17+00:00; -1s from scanner time.
| ssl-cert: Subject: commonName=DC01.SOUPEDECODE.LOCAL
| Issuer: commonName=DC01.SOUPEDECODE.LOCAL
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2025-06-17T21:35:42
| Not valid after:  2025-12-17T21:35:42
| MD5:   8660:d3bc:0e75:671b:8ffd:9a7e:fafb:60b5
|_SHA-1: 4349:710e:63b9:e96c:4a8a:c557:c8c4:d217:482f:3673
| rdp-ntlm-info: 
|   Target_Name: SOUPEDECODE
|   NetBIOS_Domain_Name: SOUPEDECODE
|   NetBIOS_Computer_Name: DC01
|   DNS_Domain_Name: SOUPEDECODE.LOCAL
|   DNS_Computer_Name: DC01.SOUPEDECODE.LOCAL
|   Product_Version: 10.0.20348
|_  System_Time: 2025-08-14T11:46:37+00:00
Service Info: Host: DC01; OS: Windows; CPE: cpe:/o:microsoft:windows

Host script results:
| smb2-security-mode: 
|   3:1:1: 
|_    Message signing enabled and required
| smb2-time: 
|   date: 2025-08-14T11:46:39
|_  start_date: N/A
|_clock-skew: mean: -1s, deviation: 0s, median: -1s
```

# Outputs:
DC01, DC01.SOUPDECODE.LOCAL, SOUPDECODE.LOCAL


# Hosts update:
echo 10.201.64.83 DC01 DC01.SOUPDECODE.LOCAL SOUPDECODE.LOCAL >> /etc/hosts && cat /etc/hosts
