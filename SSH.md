```powershell
type $env:USERPROFILE\.ssh\id_rsa.pub | ssh user@server "cat >> .ssh/authorized_keys"
```
