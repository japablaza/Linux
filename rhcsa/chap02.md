## Commands
- `lsmod | grep kvm` # KVM kernel module  
- `cat /proc/cpuinfo | grep svm or vmx` # Seach HV flag  
- `modprobe kvm_intel` # Load the kernel with intel KVM module (kvm_amd for orther cpu)  

## Virsh and Virt-* Commands
- `virsh destroy vm-name` # Shutdown vm
- `virsh undefine vm-name --remove-all-storage` # delete vm-name and image file
- Create a new VM. Example 1  
  `virt-install --name=vm-name \`
  `--ram=1024 \`
  `--vcpu=2 \`
  `--disk path=/var/lib/libvirt/images/vn-name.img,size=16 \`
  `--graphics=spice \`
  `--location=ftp://IP/pub/DIR \`
  `--os-type=linux \`
  `--os-variant=rhel7`  
  You can use `--disk size=5` # 5G in the default storage

- Create a new VM. Example 2  
  `virt-install --name=centos7-1\`  
  `--ram=1024 \`  
  `--vcpu=1 \`  
  `--os-type=linux \`  
  `--os-variant=rhel7 \`  
  `--network bridge=NAME \`  
  `--graphics none \`  
  `--console=pty,target_type=serial \`  
  `--location=http://localhost/inst \`  
  `--extra-args='console=ttyS0,115200n8 serial'`

## KVM Configuration Files
- `/etc/libvirt`
- `/var/lib/libvirt`

## Virstual Storage on a Hypervisor 
- `/var/lib/libvirt/images` # Default directory 
- Change default directory

  `semanage fcontext -a -t virt_image_t '/new_path/dir(/.*)?'`  
  `restorecon /new_path/dir`  
  `rmdir /var/lib/libvirt/images`  
  `ln -s /new_path/dir /var/lib/libvirt/images`

## Virtual Network
- How to create networks and switches with virsh?

## Virtual Disk
- How to create disks and attach to a VM with virsh?

## Virtualization Hypervisor
- `yum install libvirt qemu-kvm qemu-img` 
- Optional packages:    qemu-kvm-tools

## Virtualization Client
- `yum install gnome-boxes virt-install virt-manager virt-viewer qemu-img` 
- Optional Packages:    virt-top 
                        libguestfs-tools 
                        libguestfs-tools-c

## Virtualization Platform
- `yum install libvirt libvirt-client vurt-who qemu-img` 
- Optional Packages:    fence-virtd-libvirt 
                        fence-virtd-multicast
                        fence-virtd-serial
                        libvirt-cim
                        libvirt-java
                        libvirt-snmp
                        perl-Sys-Virt

## Virtualization Tools
- `yum install libguestfs qemu-img`
- Optional Packages:    libguestfs-java 
                        libguestfs-tools 
                        libguestfa-tools-c

