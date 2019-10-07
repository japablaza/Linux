# Mount and Copy the Installation DVD

## Mount the Standard DVD drive

- `mount -t iso9660 /dev/cdrom /media/`

## Mount an ISO file and Copy the content

- `mount -o loop file.iso /media`
- `cp -a /media/. /path/to/dir`  


- Free a loop device by hand  
  `losetup -d`  
  `umount -d`

## SELinux  

- Make sure the new files have the right SELinux with `chcon`  
  `chcon -R --reference=/var/www/html /path/to/dir`  
