# Preparing KVM and VMs

## Getting Started

- Download ISO file and check it with `sha256sum`
- `uname -p` ==> Shows architecture
- `dd if={ISO-FILE} of=/dev/{DEVIDE-ID} bs=4M status=progress` ==> Creates a bootable device, usually with a USB device.
- `yum install epel-release -y` # Extra packages
- `yum install ntfs-3g -y` #NTFS enabling support

## Apache and VSFTP

- `yum install apache`
- `systemctl start httpd`
- `mount -o loop {ISO-FILE} /media` ==> Mount ISO file
- `cp -a /media/. /var/www/html/{NEW-DIR}` ==> Copy the read-only files to a permanent location.
- `chcon -R --reference=/var/www/html /var/www/html{NEW-DIR}` ==> Right SELinux context
- `restorecon /var/www/htp/{NEW-DIR}/ks.cfg` ==> Modify Kickstart SELinux context

- `systemctl reload httpd` ==> Apache
- `yum install vsftpd`
- `mount -o loop {ISO-FILE} /media`
- `yum install vsftpd`
- `cp -a /media/. /var/ftp/{NE-DIR}`
- `chcon -R --reference=/var/ftp/pub/ /var/ftp/pub/{NEW-DIR}`
- `restorecon /var/ftp/pub/{NEW-DIR}/ks.cfg` ==> Modify Kickstart SELinux context
- `firewall-cmd --permanent --add-service=ftp` ==> Open port 21
- `systemctl start vsftpd`
- `firewall-cmd reload`

## SELinux

- `sestatus`

## Firewalld

- `firewall-cmd --list-all`
- `firewall-cmd --permanent --add-service=http` ==> Open the default port 80
- `firewall-cmd reload` ==> FW
