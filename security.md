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
- `lsattr`
- `chattr`

Permission | File | Directory
--- | --- | ---
`read (r)` | You can read files | You can see the content of the directory
`write (w)` | Write or change the file content | Create and remove files in a directory
`execute (x)` | Run the file as a program | Access the files in the directory

| Position | Short Description |
|----|----|
|  1 |  `-` ==> Regular file |
|  1 |  `d` ==> Directory |
|  1 |  `b` ==> Device |
|  1 |  `l` ==> Symbolic Link |
| 234 | Owner **rwx** |
| 567 | Group **rwx** |
| 890 | Other **rwx** |
| 11  | **.** Files with SELinux security context |
| 11  | **+** Files configured with ACL permissions |

**Example**
`-rw-r--r--. 1 root root 158 Oct  9 03:18 /etc/hosts`

| Special Permission | Executable File | Directory | Example |
| --- | --- | --- | --- |
| SUID | NEED MORE RESEARCH | | `-rwsr-xr-x.` ==> `/usr/bin/passwd`|
| SGID | NEED MORE RESEARCH | | `---x--s--x.` ==> `/usr/bin/ssh-agent` |
| Sticky bit | No effect | File in a directory can be renamed or removed only by their owner | `drwxrwxrwt.` ==> `/tmp` |

| CHMOD | Example |
| --- | --- |
| SUID = 4 | `chmod 4674 [FILENAME]` |
| SGID = 2 | `chmod g+s [FILENAME]` |
| Sticky bit = 1 | `chmod o+t [FILENAME]` |

**Find sticky bits**
`find / -type d -perm -1000`
`find . -perm 2000`
`find . -perm 4000`
`find / -perm 6000`

### Special Attributes
- `lsattr`
- `chattr`

| Attribute | Short Description | Example |
| --- | --- | --- |
| Append only (a) | Prevents deletion and allows appending to files | `chattdr +a [FILENAME]` |
| No dump (d) | Disallow backup od the configured file with the `dump` command | `chattr +d [FILENAME]` |
| Extent format (e) | Set with the `ext4` filesystem | |
| immutable (i) | Prevents deletion or any other kind of changes to a file | `chattr +i [FILENAME]` |

### Basic User and Group with UMASK
- `umask`
- `/etc/profile`
- `/etc/bashrc`

## Access Control Lists
- Override and Extend basic file permissions


## Firewall Control
- Block traffic ports
- `firewall-config`
- `firewall-cmd`
- `iptables` service ==> Chain of filter rules
- `firewalld` deamon ==> Zone-based
- `yum install firewall-config` ==> GUI-based firewall
- `/etc/services`

| Port | Short Description |
| --- | --- |
| 20, 21 | FTP |
| 22 | SSH (Secure Shell) |
| 23 | Telnet |
| 25 | SMTP (Simple Mail Transfer Protocol) Postfix, Sendmail |
| 53 | DNS (Domain Name Service server) |
| 80 | Hypertext Transfer Protocol (HTTP) |
| 88 | Kerberos |
| 110 | Post Office Protocol (POP3) |
| 139 | Network Basic Input/Output System (NetBIOS)|
| 143 | Internet Mail Access Protocol (IMAP) |
| 443 | HTTP secure |

### IPTABLES

- `iptables -t tabletype <action_direction> <package_pattern> -j <what_to_do>`
- `tabletype`: filter or NAT. Default filter
- `<action_direction>`: --append(-A), --delete(-D), --list(-L), --flush(-F)
- `<action_direction>`: INPUT, OUTPUT, FORWARD. Direction of the chain
- `<package_pattern>`: -s (source IP address), -d (destination IP address)
- `<package_pattern>`: -p (protocol) and --dport (destination port)
- `<what_to_do>`: DROP, REJECT, ACCEPT (-A INPUT/OUTPUT/FORWARD)

### FIREWALLD
- `firewall-cmd --get-default-zone`
- `firewall-cmd --set-default-zone=<zone>`

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
