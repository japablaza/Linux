## Commands
- `lsmod | grep kvm` # KVM kernel module  
- `cat /proc/cpuinfo | grep svm or vmx` # Seach HV flag  
- `modprobe kvm_intel` # Load the kernel with intel KVM module (kvm_amd for orther cpu)  
- `restorecon <file>` #Based on directory 

## Virsh and Virt-* Commands
- `virsh shutdown vm-name` 
- `virsh destroy vm-name` # Immediately power off the vm
- `virsh undefine vm-name --remove-all-storage` # delete vm-name and image file
- `virsh list --all` # shows all vms, on and off
- `virsh autostart vm-name` 
- `virsh autostart --disable vm-name`
- `virsh-clone --original=vm-name --name=new-vm-name --file=/var/lib/libvirtd/images/new-vm-name.img`

## Create New VM with Virt-install
- Example 1  Graphic
  `virt-install --name=vm-name \`  
  `--ram=1024 \`  
  `--vcpu=2 \`  
  `--disk path=/var/lib/libvirt/images/vn-name.img,size=16 \`  
  `--graphics=spice \`  
  `--location=ftp://IP/pub/DIR \`  
  `--os-type=linux \`  
  `--os-variant=rhel7`    
  You can use `--disk size=5` # 5G in the default storage

- Example 2  Console
  `virt-install --name=centos7-1 \`  
  `--memory=2048 \`  
  `--disk size=30 \`  
  `--vcpu=1 \`  
  `--os-type=linux \`  
  `--os-variant=rhel7 \`  
  `--network bridge=virbr1 \`  
  `--graphics none \`  
  `--console pty,target_type=serial \`  
  `--location=http://10.42.0.122/inst/ \`  
  `--extra-args 'console=ttyS0,115200n8 serial'`

- Example 3 Graphic/Text with kickstart  
`virt-install --name=ks_test_text \`  
`--memory=2048 \`  
`--disk size=26 \`  
`--vcpu=1 \`  
`--network bridge=virbr1 \`  
`--graphics none \`  
`--console pty,target_type=serial \`  
`--location=http://10.42.0.122/inst/ \`  
`--extra-args 'console=ttyS0, 1152200n8 serial' \`  
`--extra-args 'ks=ftp://10.42.0.122/pub/centos7/ks_text.cfg'`
  - Kickstart files: ks.cfg, ks_text.cfg, and ks_text_net.cfg

## KVM Configuration Files
- `/etc/libvirt`
- `/var/lib/libvirt`
- `/etc/libvirt/qemu/autostart`

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

# SSH Client
- `/etc/ssh/ssh_config` # SSH client config file 