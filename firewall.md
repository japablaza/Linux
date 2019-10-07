# [Firewall]

## Firewalld

### Basic Commands
- `firewall-cmd --list-all`
- `firewall-cmd --zone=public --permanent --add-service=http`
- `firewall-cmd --permanent --add-port=80/tcp
- `firewall-cmd --zone=public --permanent --add-service=https`
- `firewall-cmd --permanent --add-port=443/tcp
- `firewall-cmd --zone=public --reload`

## IPTables
- `iptables -L`
- /proc/sys/net/ipv4/ip_forward

## Router Mode for Virtual Machine
- To permanently activate IP forwarding:
  file: `/etc/sysctl.conf`
  line: `net.ipv4.ip_forward=1
  To implement the changes immediately run `sysctl -p`
