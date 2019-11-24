# Security

## Basic File Permissions
- List, Set, and change standard `ugo`/`rwx` permissions
- Users, Groups, Others ==> `UGO`
- Read, Write, Execute ==> `RWX`
- `umask` ==> Default file permissions
  - SUID
  - SGID
  - Sticky permission bits
- `chown`
- `chmod`
- `chgrp`

Permission | File | Directory
--- | --- | ---
`read (r)` | You can read files | You can see the content of the directory
`write (w)` | Write or change the file content | Create and remove files in a directory
`execute (x)` | Run the file as a program | Access the files in the directory

| Position | Shot Description |
| --- | --- |
| 1 | Type of file:   `-` ==> Regular file |

## Basic Control Lists
- Override and Extend basic file permissions

## Firewall Control
- Block traffic ports
- `firewall-config`
- `firewall-cmd`
- `iptables`

- `yum install firewall-config` ==> GUI-based firewall

# Secure Shell Server
- Configure key-based authentication for SSH

# Security Enhanced Linux
- Enforcing
- Permissive
- Disable
- Context for files and processes
- Restore default file contexts
- Boolean settings
- Diagnose and address routine SELinux policy violations
