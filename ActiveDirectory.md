# Setup IP Address
|  | DC1 | DC2 |
| --- | --- | --- |
| IP address | 10.X.100.1 | 10.X.100.2 |
| Subnet mask | 255.255.255.0 | 255.255.255.0 |
| Default gateway | 10.X.100.254 | 10.X.100.254 |
| Primary DNS | 10.X.100.2 | 10.X.100.1 |
| Secondary DNS | 127.0.0.1 | 127.0.0.1 |

# Install AD DS
```
Install-WindowsFeature -name AD-Domain-Services -IncludeManagementTools
```

# AD DS Tools
```
Install-WindowsFeature RSAT-ADDS-Tools
```



# Documentation
[Install Active Directory Domain Services](https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/deploy/install-active-directory-domain-services--level-100-)