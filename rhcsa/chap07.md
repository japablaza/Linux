# Packege Management
p8

## RPM Database
- `/var/lib/rpm`
- `rpm -V {package}` --> checksum
- `rpm -ivh {package}` --> installs the package
- `rpm -Uvh {package}` --> upgrades any existing package
- `rpm -Fvh {package}` --> upgrades only existing package
- `-vh` --> verbose mode and hash marks
- `.rpmnew` --> saved configuration file

## RPM Installation Security
- `/etc/pki/rpm-gpg` GPG keys directory
- `rpm -qa gpg-pubkey` --> check GPG keys in RPM database


## Acronyms
- GPG: GNU Privacy Guard
- PGP: Pretty Good Privacy
