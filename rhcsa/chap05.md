
## Understanding the Boot Process
- `systemctl poweroff`
- `systemctlreboot`
- `MBR` partitioning scheme supports a maimum size of 2TB per disk, GTP does not have such limitation.
- To boot from a disk with a GPT partiction layout, you need UEFI

## GRUB
- You can use `E` to temporarily edit the GRUB menu.
- You can use `C` to open GRUB2 command prompt
- Emergency Target1: press `E` and locate the line with `linux16`. At the end add `systemd.unit=emergency.atrget` and press CT
- Emergency Target2: press `E` and locate the line with `linux16`. At the end add `init=/sysroot/bin/sh` o `rd.break`
- `ls -l /etc/systemd/system/default.target` ==> Get default target
- `systemctl get-default` ==> Get default target
- p9
- `pwmake 128 | passwd --stdin <user>` ==> Change user password to random string

## Modify the System Bootloader
- `/etc/grub2.cfg` ==> GRUB2 configuration
- BIOS `/boot/grub2/grub.cfg` 
- UEFI `/boot/efi/EFI/redhat/grub.cfg`
- `grub2-mkconfig -o /boot/grub2/grub.cfg`
- `grub2-set-default <number>` ==> List available in `/etc/grub2.cfg` --> menuentry starting from 0

## Acronyms
- POST: Power On Self Test
- TPM: Trusted Platform Module
- OpenTC: Open Trusted Computing
- GTP: GUID Partition Table
- MBR: Master Boot Record
- GRUB2: GRand Unified Bootloader version 2

p13
