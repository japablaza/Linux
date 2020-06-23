# Security Options

## Firewall
- `yum install firewall-config`

## SELinux
- `enforcing`, `permissive`, `disable`

## Basic File Permissions
- `umask`, `chmod`, `chwon`, and `chgrp`
- Additional privileges can be configured with `SUID`, `SGID`, and sticky permission bits.
- Super user ID `SUID`
- Super group ID `SGID`

## File Permissions and Ownership
- `-rwxr-xr-x.` or 1234567890 position 
- First position is the type of file: `-` regular file, `d` directory, `b` device, and `l` symbolic link. 


## Acronyms
- DAC: Discretionary Access Control
- ACL: Access Control List
- MAC: Mandatory Access Control --> SELinux
- SELinux: Security-Enhanced
