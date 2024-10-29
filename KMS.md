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
Hostname	kms.domain.com
```
```
nslookup -type=srv _vlmcs._tcp.domain.com
```

# 3. Online activation
```cmd
slmgr /ato
```

# Documentation
[Windows GVLKs](https://learn.microsoft.com/en-us/windows-server/get-started/kms-client-activation-keys)

[Office GVLKs](https://learn.microsoft.com/en-us/office/volume-license-activation/gvlks)

[Key Management Services (KMS)](https://learn.microsoft.com/en-us/windows-server/get-started/kms-create-host)

[Slmgr options](https://learn.microsoft.com/en-us/windows-server/get-started/activation-slmgr-vbs-options)
