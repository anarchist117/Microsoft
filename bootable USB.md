# 1. Prepare USB Drive
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

# 2. Copy installation files without install.wim
```
install.wim = 4.57Gb
FAT32 max file size = 4Gb
```

# 2. Split install.wim
```
# D: - source disk
# E: - destination disk
Dism /Split-Image /ImageFile:D:\sources\install.wim /SWMFile:E:\sources\install.swm /FileSize:4000
```




# Documentation
[Create a bootable USB flash drive](https://learn.microsoft.com/en-us/windows-server-essentials/install/create-a-bootable-usb-flash-drive)

[Split a Windows image file (.wim)](https://learn.microsoft.com/en-us/windows-hardware/manufacture/desktop/split-a-windows-image--wim--file-to-span-across-multiple-dvds?view=windows-11)
