# Basic Regular Expression

## Regex Basics

- `^` Start of the line
- `$` End of the line
- `.` Wildcard, except newline (\n)
- `|` Matches a specific character or group on either side (a|b)
- `\` Escape a special character

## Examples

- `grep '^The ' file`
- `grep '^T[a-z]^e' file`
- `grep  '\<^[tT]the\> file`
