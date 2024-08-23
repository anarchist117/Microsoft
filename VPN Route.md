### Disable default gateway
```
Control Panel\All Control Panel Items\Network Connections => VPN Name
Internet Protocol Version 4 (TCP/IPv4) => Properties => Advanced
Uncheck "use default gateway"
```

### PowerShell
```PowerShell
Add-VpnConnectionRoute -ConnectionName "VPN Name" -DestinationPrefix 10.10.10.0/24
```
