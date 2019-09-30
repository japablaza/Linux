# Information related to RHCSA

## KVM (Kernel-based Virtual Machine)
- Installation 
  Option 1 
  `yum group install "Virtualization Host" "Virtualization Client"  
  
  Option 2  
  `yum install \  
   qemu-kvm \  
   libvirt \  
   virt-install`

## RPM (Red Hat Package Manager)
- Install RPMs  
  `rpm -ivh package.rpm`

- Check dependencies  
  `rpm -qpR package.rpm`

- List all the packages currently instelled on the local system  
  `rpm --query --all`

- List all files in all packages on the local system  
  `rpm --query -all`

- Other commands related  
  `rpmbuild`

## Key differences between RHEL 6 and RHEL 7
+ `systemd` is the service manager. Faster boot times than `Upstart` and the old `SysVinit` system.
+ XFS is the default filesystem. Supports filesystems up to  500TB in size.
+ The firewalld demon configures a zone-based firewall.
+ GNOME 3 is the default  desktop

## Linux Installation 
- Calculate the SHA256 checksum
  `sha256sum file_name.iso`
- Create a boot disk
  `dd if=name-of-image.iso of=/dev/sde bs=512k conv=fdatasync status=progress`
- RPM details is located in XML files under `/repodata`  


## ToDO 
- How to install apache?  
- How to mount ISO  
- Using `semanage`, `selinux`, and `chcon` 
- Useful command on KVM
