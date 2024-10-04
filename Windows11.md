# Clearly Installation
```
Shift + F10
regedit

HKEY_LOCAL_MACHINE\SYSTEM\Setup
New => Key => LabConfig

HKEY_LOCAL_MACHINE\SYSTEM\Setup\LabConfig
New => DWORD => BypassCPUCheck => 1
New => DWORD => BypassTPMCheck => 1
New => DWORD => BypassSecureBootCheck => 1
New => DWORD => BypassRAMCheck => 1
New => DWORD => BypassStorageCheck => 1
```


# On Windows Installed
```
regedit
HKEY_LOCAL_MACHINE\SYSTEM\Setup\MoSetup
New => DWORD => AllowUpgradesWithUnsupportedTPMOrCPU => 1
```
