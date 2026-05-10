**Table 2.1. Useful Command-line Editing Shortcuts**

|Shortcut|Description|
|:--|:--|
|**Ctrl**+**A**|Jump to the beginning of the command line.|
|**Ctrl**+**E**|Jump to the end of the command line.|
|**Ctrl**+**U**|Clear from the cursor to the beginning of the command line.|
|**Ctrl**+**K**|Clear from the cursor to the end of the command line.|
|**Ctrl**+**LeftArrow**|Jump to the beginning of the previous word on the command line.|
|**Ctrl**+**RightArrow**|Jump to the end of the next word on the command line.|
|**Ctrl**+**R**|Search the history list of commands for a pattern.|

**Wildcards**
"(*)"   |  * everything in the current directory
?      |   "characters of this size" "?? or ?????"

ls
![[Trash/SYNC/Images/Pasted image 20230921121839.png]]
	ls /bin /usr/bin | sort | uniq | grep zip
cd
![[Trash/SYNC/Images/Pasted image 20230921121350.png]]
cat
	cat *
	cat $PWD/-
	![[Trash/SYNC/Images/Pasted image 20230921152719.png]] *Power of the tab command*
file
	file $PWD/*
less
cat      |   Concatenate files
sort     |   Sort lines of text
uniq    |   Report or omit repeated lines
grep    |   Print lines matching a pattern
	grep *pattern* *filename*
	
wc       |   Print newline, word, and byte counts for each file
head    |   Output the first part of a file
tail       |   Output the last part of a file
tee       |   Read from standard input and write to standard output and files

du
pwd
find
	find . -type f -size 1033c
	find . -type f -name .file2 -size 1033c 2> /dev/null
date
cal            "*Calendar*"
df            " *To see the current amount of free space on our disk drives* "
free        *"Likewise, to display the amount of free memory"*
exit
printenv
echo 
	echo $USER
awk
cut
	
**Short-Cut**
ctrl-l   |   runs the clear command 