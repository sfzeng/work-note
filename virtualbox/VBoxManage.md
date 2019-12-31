## Create a volume and attach it to vm:
```
VBoxManage createmedium disk --filename "disk_1G" --size 1024 --format VDI --variant Fixed
VBoxManage storageattach vmname --storagectl SATA --port 3 --type hdd --medium "disk_1G.vdi"
```
### Detach & delete disk
```
VBoxManage storageattach vmname --storagectl SATA --port 3 --type hdd --medium none
VBoxManage  list hdds
VBoxManage closemedium disk disk_uuid --delete
```
### Start VM
```
VBoxManage startvm vmname -type headless
```
