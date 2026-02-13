# Setup IP Address
|  | DC1 | DC2 |
| --- | --- | --- |
| IP address | 10.X.Y.1 | 10.X.Y.2 |
| Subnet mask | 255.255.255.0 | 255.255.255.0 |
| Default gateway | 10.X.Y.254 | 10.X.Y.254 |
| Primary DNS | 10.X.Y.2 | 10.X.Y.1 |
| Secondary DNS | 127.0.0.1 | 127.0.0.1 |

# Install AD DS
```
Install-WindowsFeature -name AD-Domain-Services -IncludeManagementTools
```
### DC1
```
Install-ADDSForest -DomainName "corp.internal"
```
### DC2
```
Install-ADDSDomainController -Credential (Get-Credential CORP\Administrator) -DomainName "corp.internal"
```

# Enable Active Directory Recycle Bin
```
Enable-ADOptionalFeature -Identity 'CN=Recycle Bin Feature,CN=Optional Features,CN=Directory Service,CN=Windows NT,CN=Services,CN=Configuration,DC=corp,DC=internal' -Scope ForestOrConfigurationSet -Target 'corp.internal'
```

# AD DS Tools
```
Install-WindowsFeature RSAT-ADDS -IncludeAllSubFeature
```



# Documentation
[Best practices for DNS client settings in Windows Server](https://learn.microsoft.com/en-us/troubleshoot/windows-server/networking/best-practices-for-dns-client-settings) </br>
[Install Active Directory Domain Services](https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/deploy/install-active-directory-domain-services--level-100-) </br>
[.internal](https://en.wikipedia.org/wiki/.internal) </br>
[Enable Active Directory Recycle Bin](https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/get-started/adac/active-directory-recycle-bin?tabs=powershell#enable-active-directory-recycle-bin)