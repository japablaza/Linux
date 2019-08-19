# Information related to RHCSA

## KVM (Kernel-based Virtual Machine)
- Installation 
	

## RPM (Red Hat Package Manager)
- Install RPMs
> `rpm -ivh package.rpm`

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
