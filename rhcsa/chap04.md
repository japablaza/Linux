# Security Options
p25
## Firewall
- `yum install firewall-config` ==> Graphical utility.
- `yum install firewall-cmd` ==> Command tool.
- The kernel comes with the netfilter system: packetfiltering, network address translation, and load balancing
- The `iptables` tools comes with services to manage the firewall rules: `iptables servie` and `firewall deamon` 
- List of services, ports, and protocols `/etc/services`

### IPTABLES
- `iptables -t tabletype <action_direction> <packet_pattern> -j <what_to_do>`
- `t tabletype` : *filter* or *nat*. The default is filter.
- `action_direction`: *-A (--append)*, *-D (--delete)*, *-L (--list)*, *-F (--flush)*
- `action_direction`: *INPUT*, *OUTPUT*, *FORWARD*
- `packet_pattern`: Source *-s ip_address*, Destination *-d ip_address*
- `packet_pattern`: Protocol *-p TCO/UDP*, Destination port *--dport {Number}*
- `what_to_do`: *DROP*, *REJECT*, *ACCEPT*
- `what_to_do`: Accept *-A INPUT/OUTPUT/FORWARD*

## SELinux
- `enforcing`, `permissive`, `disable`

## Basic File Permissions
- `umask`, `chmod`, `chwon`, and `chgrp`
- Additional privileges can be configured with `SUID`, `SGID`, and sticky permission bits.
- Super user ID `SUID`
- Super group ID `SGID`
- `find /bin -perm /4000` ==> Finds the files with `SUID`
- `find /bin -perm /2000` ==> Finds the files with `SGID`
- `find / -type d -perm /1000` ==> Finds the directories with sticky bit
- `Add the `-exec ls -l '{}' \;` to see the permissions

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
- `chmod 4664 my_file` ==> `SUID` bit
- `chmod g+s mi_archivo` ==> `SGID` bit
- `chmod o+t /directorio` ==> Sticky bit
- `/etc/profile` and `/etc/bashrc` ==> Default umask
- `umask` default for files 644 and for directory 755. ==> Root user
- `umask` default for files 664 and for directory 775

## Special File Attributes
- `lsattr`
- `chattr`
- Attribute: `chattr +a`, `chattr +d`, `chattr +i`, or `chattr +e`.

## Access Control List
- You need to mount the appropriate filesystem with the `acl` option. 
- The directory in the filesystem needs execute permissions.
- ACLs is supportted on `ext4`, `xfs`, and `NFS` version 4.
- `tune2fs -l /dev/sdaX` will show you the `acl` option.  `Tune2fs` works on `ex2/ext3/ext4` only
- `mount -o remount -o acl /DIRECTOY` will enable `acl`.
- `getfacl FILE`
- `setfacl -m u:USER:rwx /FILE` ==> Set the permission `rwx`
- `setfacl -x u:USER /FILE` ==> Removes USER permissions
- `setfacl -m u:USER:- /FILE` ==> Removes all pemissions
- `setfacl -b /FILE` ==> Removes all ACL entries
- `setfacl -m o:- /FILE` Removes permissions for others

## NFS Shares and ACLs
- `nfs4-acl-tools` package
- `nfs4_getfacl` 

## Acronyms
- DAC: Discretionary Access Control
- ACL: Access Control List
- MAC: Mandatory Access Control --> SELinux
- SELinux: Security-Enhanced
- PAM: Pluggable Authentication Module
- NAT: Network address translation
- TCP: Transmission Control Protocol
- UDP: User Datagram Protocol
- SCTP: Stream Control Transmission
