# SELinux User's and Administrator's Guide

## LINK
  `https://wiki.centos.org/HowTos/SELinux`
  `https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/selinux_users_and_administrators_guide/index`

## Description
> SELinux (Security Enhanced Linux) is a Linux Kernel Security modeule that allows administrator and user more control over access controls. It allows access based on SELinux pilicy rules
> SELinux policy rules specify how processes and users interact with each other as well as how processes and users interact with files.

## SELinux security model
- Subject: Process
- Objects: File, Device, a socket
- Actions : What can you do with the Object
- Context to Objects: Context is a label

## SELinux Label
- User context: `_u`
- Role context: `_r`
- Type context: `_t`
- Sensitivity context: `s0-s0`
- Category Set: `c0.c1023`
- `/etc/selinux/targeted/contexts/files`
- `/sys/fs/selinux/boolean`
- `getsebool -a`
- `semanage boolean -l`

## SELinux modes
- Enforcing: SELinux allows access based on SELinux policy rules.
- Permissive: SELinux only logs actions that would have been denied if running in enforcing mode.
- Disabled: No SELinux policy is loaded

## Basic commands
- `sestatus` --> SELinux status
- `/usr/sbin/getenforce` --> SELinux mode

## Disable SELinux. Reboot is needed
- `setenforce 0` --> SELinux mode from `targeted` to `permissive`
- `echo -n 0 > /sys/fs/selinux/enforce`
- `setenforce Permissive`
- `vi /etc/sysconfig/selinux` --> Set SELINUX=disable
  `/etc/selinux/config` --> Symbolic Link from `/etc/sysconfig/selinux`
