# Documentation

## Man pages

- uses `vim` keybindings
- `man -k`
  - Man pages sections:
    - 1: Executable programs or shell commands
    - 5: File formats and conventions
    - 8: System administration commands
- `man -f` ==> `whatis`
- `mandb`

## Info pages

- `info`
- Uses `emacs` keybindings/commands

## USR directory

- `/usr/share/doc`
- Search for a specific document
  - `ls -la /usr/doc/share | egrep -i "command1|command2|command3"
- Can be in many formats: TXT, MD, HTML, CSS, PNG, etc.

## Other commands

- `apropos [keyword]`  ==> `apropos http`
- `whatis [command]`   ==> `whatis egrep`
- `which -a [command]` ==> `which -a egrep`
- `whereis [command]`  ==> `whereis python`
