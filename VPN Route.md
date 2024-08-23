# Import CA root
```PowerShell
Import-Certificate -FilePath root.crt -CertStoreLocation Cert:\LocalMachine\Root\
```
# Import User cert
```PowerShell
Import-PfxCertificate -FilePath user.p12 -CertStoreLocation Cert:\CurrentUser\My -Exportable
```
# Add VPN connection IKEv2
```PowerShell
$EAPXml = Get-Content -Path "VPN EAP.xml"
Add-VpnConnection -Name "VPN Name" -ServerAddress vpn.domain.com -TunnelType Ikev2 -EncryptionLevel Required -AuthenticationMethod Eap -SplitTunneling -EapConfigXmlStream $EAPXml
```

### Disable default gateway
```
Control Panel\All Control Panel Items\Network Connections => VPN Name
Internet Protocol Version 4 (TCP/IPv4) => Properties => Advanced
Uncheck "use default gateway"
```

### Add an IPv4 route to a specified VPN connection
```PowerShell
Add-VpnConnectionRoute -ConnectionName "VPN Name" -DestinationPrefix 10.10.10.0/24
```
