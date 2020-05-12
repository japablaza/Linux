# Command line

## Virtual Terminals (TeleType)
- `/etc/systemd/logind.conf`
- Virtual Terminal associated to `/dev/ttyN` where N is the terminal number
- Number of virtual terminals limited by `/etc/securetty`

## Text Stream
- Standard input  `stdin`
- Standard output `stdout`
- Standard error  `stderr`
- Append output to the end of the file `ls >> file`
- Save error in the file `script 2> file`
- Redirect the error stream to the special device `script 2> /dev/null`
- Standard and error output to a file `script &> file`
- Reverse search from terminal `CTRL-r`

## Directory and Environment $PATH
- Absolute paths: Complete directory structure
- Relative paths : Is is based on the current directoy 
- `echo $PATH`
- `/etc/profile`
- `/etc/profile.d/`
- `~/.bash_profile`
- `~/.profile`

## Commands
- `pwd`: Print Working Directory 
- `~`: The tilde represent the user home directory
- `touch`: Create a new file and change the time of the last modification 
- `cp -a`: support recursive changes and preserves all file attributes