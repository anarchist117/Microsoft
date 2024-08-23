# Import CA root
```PowerShell
Import-Certificate -FilePath root.crt -CertStoreLocation Cert:\LocalMachine\Root\
```
# Import User cert
```PowerShell
Import-PfxCertificate -FilePath user.p12 -CertStoreLocation Cert:\CurrentUser\My -Exportable
```
# Add VPN connection
```PowerShell
# Import EAP configuration (User Certificate)
$EAPXml = Get-Content -Path "VPN EAP.xml"
```
```PowerShell
# Add VPN connection IKEv2 without default route
Add-VpnConnection `
    -Name "VPN Name" `
    -ServerAddress vpn.domain.com `
    -TunnelType Ikev2 `
    -EncryptionLevel Required `
    -AuthenticationMethod Eap `
    -EapConfigXmlStream $EAPXml `
    -SplitTunneling
```

### Add an IPv4 route to a specified VPN connection
```PowerShell
Add-VpnConnectionRoute -ConnectionName "VPN Name" -DestinationPrefix 10.10.10.0/24
```



[# EAP configuration](https://learn.microsoft.com/en-us/windows/client-management/mdm/eap-configuration)
