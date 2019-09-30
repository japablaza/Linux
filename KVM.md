[Hypervisor]

- VM Level: VMware Player or VirtualBox
- Bare-Metal Hypervisor: VMware ESXi and Citrix XenServer
- KVM replaced Xen

[Containers]
- RHEL Atomic Host Project

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
