# Packege Management
p28

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
- `rpm -ivh kernel.rpm` or `yum install kernel` are the best option for upgrading to a new kernel. 
- Upgrade to a new kernel will add a new option in the GRUP `/boot/grub2/grub.cfg`

## More RPM Commands

- `rpm -qa` ==> Lists all installed packages
- `rpm -qf {FILE_PATH}` ==> Identifies the packages associated with the FILE
- `rpm -qc {Package_Name}` ==> Configuration files only
- `rpm -qd {Package_Name}` ==> Documentation files only
- `rpm -qi {Package_Name}` ==> Basic information 
- `rpm -ql {Package_Name}` ==> All files for package
- `rpm -qR {Package_name}` ==> Dependencies
- `rpm -q --changelogs {Package_Name}` ==> Change logs
- `rpm -Va` or `rpm --verify -a` ==> Verify all files on your system
- `rpm --verify -p {Package_Name}` ==> Verifies the package name

- `rpm -qlp {Local_Package}` ==> All files for package
- `rpm --checksig {Local_Package}`  ==> Checks the integrity of the package

## YUM to the rescue

- ` yum-config-manager` ==> The full list of yum configuration
- `/etc/yum.repos.d/` ==> Configuration files
- New repo file under `/ect/yum.repo.d/{file_name}.repo
- New repo file must contain: _repositoryid_, _name_, and _baseurl_
- Update the local DB cache with `yum clean all` and `yum makecache`
- New rep from ISO file: `mount -o loop {file.iso} {/temp_dir}`, `cp -a /temp_dir/. {/local/dir}`, and then create the repo file with `baseurl=file///local/dir/.}`


## Acronyms

- GPG: GNU Privacy Guard
- PGP: Pretty Good Privacy
- EPEL: Extra Packages for Enterprice Linux
- PKI: Public Key Infrastructure
