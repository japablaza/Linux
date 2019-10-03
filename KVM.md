# Kernel-based Virtual Machine  

[Hypervisor]

- VM Level: VMware Player or VirtualBox
- Bare-Metal Hypervisor: VMware ESXi and Citrix XenServer
- KVM replaced Xen

[Containers]
- RHEL Atomic Host Project

## Packages and Installation  

### Essential Packages
Packages | Description
--- | ---
qemu-kvm | The main KVM package
libvirt | The libvirtd service to manage hypervisors
libvirt-client | The virsh command and client API to manage virtual machines
virt-install | Command-line tools for creating VMs
virt-manager | GUI VM administration tool
virt-top | Command to display virtualization statistics
virt-viewer | Graphical console to connect to VMs

### Group of Packages
Packages | Description
--- | ---
Virtualization Host | Hypervisor
Virtualization Client | Hypervisor client 

### Helpful Packages
Packages | Description
--- | ---
libguestfs-tools | Display the content of a VM disk or manage VM partitions and filesystems from the hypervisor host  
## Useful Commands  

[virt-install]

```
virt-install \
--name=vm1 \
--ram=2048 --vcpus=1 \
--location=http://localhost/install \
--disk path=/var/lib/libvirt/images/vm1.img,size=16 \
--network bridge=virbr01 \
--os-type=linux \
--os-variant=rhel7 \
--graphics=spice
```
