# Filesystem

p20 

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

## Acronyms
- MBR: Master Boot Record
- GPT: GUID Partition Table
