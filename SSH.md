```powershell
type $env:USERPROFILE\.ssh\id_rsa.pub | ssh root@server "cat >> .ssh/authorized_keys"
```
