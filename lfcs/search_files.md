# Search Files

## Find

- `find /etc -name "sshd_config"`
- `find /etc -iname "ssh_config"` Insensitive case
- `find /etc -type l` Finds links under etc directory
- `find / -type f -user pepe` Finds files by username

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
