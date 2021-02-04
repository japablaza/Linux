# Archive files

## Create a tar file

- `tar cvf etc.tar /etc/ssh` Archives ssh directory
- `tar cvf file.tar /dir/file1 /dir2/file2 /home/user`
- `tar --exclude='.*' -cvf file.tar /home/user` Excludes hidden files

## Compress and extract (gzip/bz2)

- `tar cvzf etc.tar.gz /etc/ssh` Archives and compress the ssh directory
- `tar cvzf file.tgz /home/user`
- `tar cvfj file.tar.bz2 /home/user`
- `tar cvfj file.tar.tbz /home/user`
- `tar cvfj file.tar.tb2 /home/user`

## Extract

- `tar xvfz etc.tar.gz` Extracts the content of etc.tar.gz in the current directory
- `tar xvf file.tar -C /extract_dir` Extracts in a different directory
- `tar --extract --file=file.tar 'file1'` Extracts single file
- `tar zxvf file.tar.gz 'file1' 'file2'` Extracts file1 and file2
- `tar xvf file.tar --wildcards '*.log'`

## List tar file

- `tar tvf etc.tar` List the files and directory on the tar file

## Append Files and Directories

- `tar rvf file.tar file1`
- `tar rvf file.tar dir`
- `tar --append --file=file.tar newfile`
