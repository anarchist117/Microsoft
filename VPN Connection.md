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
$EAPXml = '<EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"><EapMethod><Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type><VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId><VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType><AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId></EapMethod><Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"><Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"><Type>13</Type><EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"><CredentialsSource><CertificateStore><SimpleCertSelection>true</SimpleCertSelection></CertificateStore></CredentialsSource><ServerValidation><DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation><ServerNames></ServerNames></ServerValidation><DifferentUsername>false</DifferentUsername><PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">true</PerformServerValidation><AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">true</AcceptServerName></EapType></Eap></Config></EapHostConfig>
'
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


# Documentation
[EAP configuration](https://learn.microsoft.com/en-us/windows/client-management/mdm/eap-configuration)

