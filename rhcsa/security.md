# Security options
- `DAC`: Descretionary Access Controll
 
## File Permissions
###Default permissions
- Set the default file permissions with `umask`. 
- Permission and Ownership: Read, Write, Execute by User, Group, Others
- Managing permissings with `chmod`, `chown`, and `chgrp`

### Special permissions
- `SUID`: Super User ID
Example: `ls -l /usr/bin/passwd`
`-rwsr-xr-x. 1 root root` Can be executed by other users with the authority of Root

- `SGID`: Super Group ID
Example: `ls -l /usr/bin/ssh-agent`
`---x--s--x. 1 root nobody`

- `Stiky permissions bits`
Example: `ls -l /tmp`
`drwxrwxrwt. 22 root root`  

## Access Control Lists

## Firewall
### IPTABLES

### FIREWALLD

## SSH

## SELinux
