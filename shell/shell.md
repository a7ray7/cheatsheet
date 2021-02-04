# Shell 🍎 🐧

<!-- This file needs better organization -->

Alias to create a directory and then immediately switch to it
`alias mds='mds(){mkdir -p "$1" && cd "$1"}; noglob mds'`

Alias for git fetch with prune option
`alias gfp='git fetch --prune'`

Give no. of line as integer
`wc -l file.txt | awk '{ print $1 }'`

Extracts anything after the match. Here the match is "^.*Tmp, "
`sed -n -e 's/^.*Tmp, //p'`

Print 5th line of the file file.txt
`sed '5q;d' file.txt`

Remove last line in a file.txt
-i : in-place
$  : last line
d  : delete
`sed -i '$d' file.txt`

for macOS, to disable backup file to be created by OS add extra '' to not create a backup file
`sed -i '' '$d' file.txt`
