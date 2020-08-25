# Filesystem

p31 

## Partition Management
- `fdisk` or `parted` to create an MBR-style partition.
- `fdisk` does not support GPD partitions.
- `parted` and `gdisk` do support GPD partitions. 
- `df` and `fdisk -` 
- `mount` shows the format and mount point
- `findmnt` shows all ,mounted filesystems in a tree-like format

## The fdisk, gdisk, and parted Utility
- After creating a new partition, you could use `partprobe /dev/{DISK}` to update the Kernel with the new partition table.
- MBR uses 32-bit logical addresses and up to 2TB.
- GPT support up to 128 partitions.
- GPT uses 64-bit logical addresses and up to 8 million terabytes, wow!
- `parted` writes changes immediately. 
- You can change the partition type with the `set` option.

## Swap Partition
- Using fdisk or parted select the type of partition, file system, and size.
- Format the swap partition with `mkswap /dev/vdX#`
- Activate the swap partition with `swapon /dev/vdX#`

## Standard Formatting and Journaling
- `mkfs -t xfs /dev/sdX#` 
- `mkfs.xfs /dev/sdX#`

## Filesystem Check Commands
- `fdck`
- `e2fsck`
- `dumpe2fs -h /dev/vdX# | grep features`
- `ls -i` --> Check the inode
- `xfs_admin -u /dev/mapper` --> Displays the UUID
- `mount -o remount,ro {PATH\DIR}`
- `mount -o remount,acl {PATH\DEVICE} {PATH\DIR}`
- `mount -o loop {ISO-FILE} {PATH\DIR}`

## Filesystem Mount Options
- `/etc/fstab`

## Virtual Filesystems
- `/etc/mtab`

## Filesystems and Directories
- https://en.wikipedia.org/wiki/Filesystem_Hierarchy_Standard
- Mounted directories  == Volumes
- `/proc` and `/sys` directoriesare filled only during the boot process

## Logical Volume Management
- `pvcreate {/dev/vdX#} {/dev/vdX#}`
- `pvdisplay`
- `vgcreate {GROUP_NAME} {/dev/vdX#} {/dev/vdX#}`
- `vgdisplay`
- `vgextend {GROUP_NAME} {/dev/vdX#} {/dev/vdX#}`
- `lvcreate -L {+MG} {GROUP_NAME} - {NAME_LV}`

## Create and Attach a New Disk with virsh

- Create a new virtual disk
```
qemu-img create -f raw /var/lib/libvirt/images{new-disk-image} {size}
qemu-img create -f qcow2 /var/lib/libvirst/images/{new-disk-image.qcow2} {size}
```

```
dd if =/dev/zro of={name-disk-image} bs=1M count=5120 status=progress
```

- Attach a new disk permanently
```
virsh attach-disk {VM-Name} \
--source /var/lib/libvirt/images/{new-disk-image} \
--target vdX \
--persistent
--subdriver qcow2
```

- Attach a new disk temporarily
```
virsh attach-disk {VM-name} \
--source /var/lib/libvirt/imges/{new-disk-image} \
--target vdX \
--cache none
```

## Acronyms
- MBR: Master Boot Record
- GPT: GUID Partition Table
- HSFS: High Sierra File System --> ISO 9660
- FHS: Filesystem Hierarchy Standard
- LVM: Logical Volume Manager
- PVs: Physical Volumes
- VGs: Volume Groups
- PEs: Physical Extents
- UUID: Universally Unique Identifiers
