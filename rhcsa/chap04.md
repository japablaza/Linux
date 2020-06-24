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
- `SUID` the user can execute the file for himself but not for others. `ls -lZ /usr/bin/passwr`.
- `SGID` 
- Sticky bit keeps file protected and only the owner can delete them. `ls -ld /tmp`.
- Write permission on directory might overwrite write permission on files. `vi:w!` -->  overwrite file.

## Change Permissions and Ownership
- `chmod`, `chown`, and `chgrp`.
- Numeric bit for `SUID`= 4, `SGID`= 2, and Stiky bit = 1
- `umask` default for files 664 and for directoy 775.

## Special File Attributes
- `lsattr`
- `chattr`
- Attribute: `chattr +a`, `chattr +d`, `chattr +i`, or `chattr +e`.

## Access Control List
- You need to mount the appropriate filesystem with the `acl` option. 
- The directory in the filesystem needs execute permissions.
- ACLs is supportted on `ext4`, `xfs`, and `NFS` version 4.
- `tune2fs -l /dev/sdaX` will show you the `acl` option. 
- `mount -o remount -o acl /DIRECTOY` will enable `acl`.
- `getfacl FILE`
- `setfacl -m u:USER:rwx /FILE` 

## Acronyms
- DAC: Discretionary Access Control
- ACL: Access Control List
- MAC: Mandatory Access Control --> SELinux
- SELinux: Security-Enhanced
- PAM: Pluggable Authentication Module