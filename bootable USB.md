# Diskpart
```
list disk
select disk <X>
clear
create partition primary
select partition 1
format fs=fat32 quick
active
exit
```

# Documentation
[Create a bootable USB flash drive](https://learn.microsoft.com/en-us/windows-server-essentials/install/create-a-bootable-usb-flash-drive)
