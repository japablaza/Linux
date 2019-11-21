# Command Line Skills  

Metacharacter losing its special meaning, precede it by a backslash `\`

## Wildcard  or Globbing  

Wildcard | Short description  
--- | ---  
`*` | Return any number or character  
`?` | Return one single character  
`[]` | Return a range of options. You can also use use the range [1-5]  
`$LANG` |  
`$LC_ALL` |  
`\` |  

## File Searches  

### Find  
- `find [DIRECTORY] -name [FILENAME]`  

### Locate  
- Documentation `/etc/cron.daily/mlocate`
- ` updatedb`
- `locate`  

## Commands to Read Text Streams  
- `cat`  
- `less` and `more` ==> These are called *pagers*  
- `head` and `tail`
- `tail -f -n 100 [FILENAME]`  

## Commands to Process Text Streams  
- `sort`  
- `grep`  
- `grep -i [FILENAME]` ==> case-insensitive  
- `grep -E [FILENAME]` ==> Enable the use of extended regular expression syntax  
- `grep -v '^$' /etc/ssh/sshd_config | grep -v '^#'`  
- `diff`  
- `wc`  

### SED  
- `sed 's/[FINDWORD]/[REPLACEWORDWITH]/' [FILENAME] > [OUTPUTFILE]`  
- `sed 's/[FINDWORD]/[REPLACEWORDWITH]/g' [FILENAME] > [OUTPUTFILE]`

### AWK  
- `awk -F : '[WORD] {print $[COLUMN]}' [FILENAME]`

### VI
- `vipw` ==> `/etc/passwd`
- `vigw` ==> `/etc/group`
- `visudo` ==> `/etc/sudoers`  
- `vipw -s` ==> `/etc/shadow`  
- `vigr -s` ==> `/etc/gshadow`

## Special Characters in Regular Expressions  

Metacharacter | Short Description  
--- | ---
`.` | Any single character  
`[]` | Match the characters included. Use range  
`?` | Match the proceding element zero or one time  
`+` | Match the preceding element one or more times  
`*` | Match the preceding element zero or more times  
`^` | Match the beginning of a line.  
`$` | Match the end of a line  
