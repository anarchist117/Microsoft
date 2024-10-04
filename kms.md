# 1. Install a product key
```cmd
slmgr /ipk <product key>
```

# 2. Set KMS Server or Create SRV record
```cmd
slmgr /skms kms.domain.com
```
```
Manually create DNS records
Type		SRV
Service/Name	_vlmcs
Protocol	_tcp
Priority	0
Weight		0
Port number	1688
Hostname	FQDN of the KMS host
```
```
nslookup -type=srv _vlmcs._tcp.domain.com
```

# 3. Online activation
```cmd
slmgr /ato
```

# Documentation
[Key Management Services (KMS) client activation and product keys](https://learn.microsoft.com/en-us/windows-server/get-started/kms-client-activation-keys)

[How to create a Key Management Services (KMS) activation host](https://learn.microsoft.com/en-us/windows-server/get-started/kms-create-host)

[Slmgr.vbs options for obtaining volume activation information](https://learn.microsoft.com/en-us/windows-server/get-started/activation-slmgr-vbs-options)
