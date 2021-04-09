# Shell 🍎 🐧

<!-- This file needs better organization -->

---

## Alias
  
`alias mds='mds(){mkdir -p "$1" && cd "$1"}; noglob mds'` Alias to create a directory and then immediately switch to it  
`alias gfp='git fetch --prune'` Alias for git fetch with prune option  

---

## File/Text Manipulation

`wc -l file.txt | awk '{ print $1 }'` Give no. of line as integer  

`sed -n -e 's/^.*Tmp, //p'` Extracts anything after the match. Here the match is `^.*Tmp, `  
`sed -n -e 's/:.*//p'` Removes anything after the colon in all lines in a file. This is how the match happens using ":.*"  
`sed '5q;d' file.txt`  Print 5th line of the file file.txt  
`sed -i '$d' file.txt`  Remove last line in a file.txt;  -i : in-place;  $  : last line ; d  : delete  
`sed -i '' '$d' file.txt`  for macOS, to disable backup file to be created by OS add extra '' to not create a backup file  

`tail -r <file-name>` shows all the contents of the file in reverse order i.e. last line 1st to 1st line last.  
`tail -rq DIR/**` shows all the contents in reverse order for all the files in DIR folder and removes headers 

---

## Shell

`precmd() { print "" }`  To add a new line after a commandline execution is finished(in `zsh`)  

---
