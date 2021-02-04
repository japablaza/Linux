# Search Files

## Find

- `find /etc -name "sshd_config"`
- `find /etc -iname "ssh_config"` Insensitive case
- `find /etc -type l` Finds links under etc directory
- `find / -type f -user pepe` Finds files by username

### Find Options

- `find /usr -size +10M -exec du -h {} \;` Shows files larger than 10MB
- `find /usr -type f -perm -4000` Shows files with SUID
- `find /etc atime -5` Accessed less than five days ago
- `find /etc -mtime +3` Files modified more than three days ago.

## Locate

- `updatedb`
- `locate file.name`
- `locate -i file.name` Insensitive case

## Which

- `which python`

## Whereis

- `whereis python | tr " " '\n'`

## Type

- `type ls`
- `type -a ls`
