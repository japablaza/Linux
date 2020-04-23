## Documentation
- `/usr/share/doc`

## Commands
- `uname -p` --> show the architecture 
- `sha256sum` --> check the ISO file
- `dd bs=4M if=file.iso of=/dev/sdd conv=fdatasync status=progress`
- `sestatus`
- `firewall-cmd --list-all`
- `mount -o loop file.iso /directory`
- `yum install epel-release -y` # Extra packages
- `yum install ntfs-3g -y` #NTFS enabling support
- `chcon -R --reference=PATH new_PATH` # SELinux context
- `firewal-cmd --permanent --add-service=http`