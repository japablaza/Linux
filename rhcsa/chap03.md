# Command line

## Other Shells
- `bash`, ` ksh`, `tcsh`, and `zsh`
- Change your default shell at the end of the user line `/etc/passwd`
- Check the current shell `echo $0` or `ps -p $$`

## Virtual Terminals (TeleType)
- `/etc/systemd/logind.conf`
- Virtual Terminal associated to `/dev/ttyN` where N is the terminal number
- Number of virtual terminals limited by `/etc/securetty`

## Text Stream
- Standard input  `stdin`
- Standard output `stdout`
- Standard error  `stderr`
- Append output to the end of the file `ls >> file`
- Save error in the file `script 2> file`
- Redirect the error stream to the special device `script 2> /dev/null`
- Standard and error output to a file `script &> file`
- Reverse search from terminal `CTRL-r`

## Wildcard
- `*`: Any number of characters or no characters at all
- `?`: One single character
- `[]`: A range of options. [1-3] range from 1 to 3.

## File Searches
- `find /bin -name name.conf`: Search for name.conf in the directory /bin
- `locate` updates once a day or running `updatedb`. `/etc/cron.daily/mlocate`

## Process Text Streams
- `sort`
- `grep -i`: case-insensitive. `grep -v` reverses the matching logic

## Regular Expression
- `.` single character.
- `[]` match character.
- `?` match the preceding character zero or once.
- `+` match the preceding character one or more times.
- `*` match the preceding character zero or more times.
- `^` match the beginning of the line.
- `$` match the end of the line.

## Directory and Environment $PATH
- Absolute paths: Complete directory structure
- Relative paths : Is is based on the current directoy 
- `echo $PATH`
- `/etc/profile`
- `/etc/profile.d/`
- `~/.bash_profile`
- `~/.profile`
- UID 0 corresponds to the root user

## Local Online Documentation
- `man`
- `whatis COMMAND`
- `apropos`
- `/etc/cron.daily/man-db.cron`
- `ls /usr/share/info`
- `info COMMAND`
- `pinfo COMMAND`
- `/usr/share/doc`

## IPv4 Networks
- RTT: Round trip time
- TTL: Time-to-Live
- CIDR: Classless Inter-Domain Routing
- `ip -s link`: shows the link status with Rx and Tx
- `ip addr`: shows all the interfaces IP information 
- `ip addr add IP/CIDR dev NAME`: Assigns an IP address and netmask to NAME
- `ip route`: shows the routing table
- `ss -tupna`: Shows all listening and non-listening sockets and it program
- `traceroute` relies on UDP probes packets. Option `-I` or `-T` enable ICMP or TCP probe packets
- `ip link set dev NAME up`: Device UP.
- `ip link set dev NAME down`: Device DOWN.
- `ip addr flush dev NAME`: Removes all IP addresses.
- `ip link set dev NAME txqlen N`: Changes the length of the transmit queue.
- `ip link set dev NAME mtu N`: Sets the maximum transmission unit as N, in bytes.
- `ip link set dev NAME promisc on`: Activates promiscuous mode.
- `ip neigh`: Displays a table of a hardware and IP addresses.
- `dhclient INTERFACE`
- `ss -tuna4`: Displays networks connections
- `nmcli dev status`
- `nmtui`: Text-based graphical tool
- `nm-connection-editor`: GUI
- `nmcli con show`
- `nmcli con reload`
- `nmcli con add con-name 'NAME' type ethernet ifname eth0`
- `nmcli con mod 'NAME' ipv4.addresses 'IP-ADDRESS/CIDR`

## Network Configuration Files
- `systemctl status network`
- `/etc/sysconfig/network-scripts`
- `systemctl status NetworkManager`

## Name Resolution
- `/etc/hostname`
- `/etc/resolv.conf`: Location of DNS servers
- `/etc/hosts`: Static DB of hostnames/FQDNs and IPs
- `/etc/nsswitch.conf`: DB search priorities

## Commands
- `pwd`: Print Working Directory 
- `~`: The tilde represent the user home directory
- `touch`: Create a new file and change the time of the last modification 
- `cp -a`: support recursive changes and preserves all file attributes
- `ln`: Creates hard and soft links. Hard links are directory entries that point to the same inode. Soft links serves a s redirect
- `mkdir -p /dir01/dir02/dir03`: Creates a series of directories 
- `file *`: Determine the type file (text, executable, or data/binary)
- `type`: Describes the command. Example `type cp` 
- `less` can read text files compressed in gzip format
- `grep -v '^$' FILE | grep -v '^#'` Select only the lines from file are not blank and without a comment
- `grep -v -e '^$' -e '^#' FILE` Same resoult ^^
- `awk -F : '/USERNAME/ {print $7}' FILE`
- `ping`
- `traceroute`
- `tracepath`

## VIM
- `vimtutor`
- `visudo` opens `/etc/sudoers`
- `vipw` opens `/etc/passwd`
- `vigr` opens `/etc/group`
- `vipw -s` opens `/etc/shadow`
- `vigr -s` opens `/etc/gshadow`

