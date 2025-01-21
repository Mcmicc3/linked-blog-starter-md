stdIN: 0
stdOUT: 1
stdERROR: 2

Over the wire - fun way to learn Linux
- bandit
How to log out of user account
- exit

Level 1 commands: [ls](https://man7.org/linux/man-pages/man1/ls.1.html) , [cd](https://man7.org/linux/man-pages/man1/cd.1p.html) , [cat](https://man7.org/linux/man-pages/man1/cat.1.html), [file](https://man7.org/linux/man-pages/man1/file.1.html), [du](https://man7.org/linux/man-pages/man1/du.1.html), [find](https://man7.org/linux/man-pages/man1/find.1.html)

# Level 0
The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.
~$ ls
~$ cat readme
*or*
~$ cat *
lvl1: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If

# Level 1
The password for the next level is stored in a file called - located in the home directory
~$ cat $PWD/-     "*or*"
~$ cat /home/bandit1/-  "*or*"
~$ cat ~/-

"Can only be opened through absolute path"
Absolute path: pwd
Lvl2: 263JGJPfgU6LtdEvgfWU1XP5yac29mFx

# Level 2
The password for the next level is stored in a file called spaces in this filename located in the home directory
~$ cat "spaces in this filename"
**"or"**
~$ cat  spa  [tab]
~$ cat spaces\ in\ this\ filename
**"or"**
~$ cat $PWD/*
Lvl3: MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx

# Level 3
The password for the next level is stored in a hidden file in the inhere directory.

~$ ls 
~$ cd inhere
~$ ls -a
~$ cat .hidden
Lvl4: 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ

# Level 4
The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.

~$ cd inhere
~$ ls
~$ for x in {0..9}; do file ./-file0$x; done
~$ cat $PWD/-file07
or
~$ file $PWD/*
~$ cat /home/bandit4/inhere/-file07
lvl5: 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw


# Level 5
The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:

- human-readable
- 1033 bytes in size
- not executable

~$ ls
~$ ls -alpRs
~$ cd maybehere07
~$ cat $PWD/.file2
"*or*"
~$ find . -type f -size 1033c
"*or*"
~$ find .-type f -name .file2 -size 1033c 2> /dev/null
"*or*"
~$ find -type f -size 1033c ! -executable
lvl6: HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
# Level 6
The password for the next level is stored somewhere on the server and has all of the following properties:

- owned by user bandit7
- owned by group bandit6
- 33 bytes in size

~$ _find / -user bandit7 -group bandit6 -size 33c 2>/dev/null_

_/ from root folder_
_-user the owner of the file._
_-group the group owner of the file._
_-size the size of the file._
_2>/dev/null redirects error messages to null so that they do not show on stdout._

~$ cat /var/lib/dpkg/info/bandit7.password
lvl7: morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj

# Level 7
The password for the next level is stored in the file data.txt next to the word millionth

Level 7 commands: [man](https://man7.org/linux/man-pages/man1/man.1.html), grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

~$ ls
*data.txt*
~$ grep "millionth" data.txt
**or**
~$ sort data.txt | grep millionth

level 8: dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc

# Level 8
The password for the next level is stored in the file data.txt and is the only line of text that occurs only once

#### Commands you may need to solve this level
grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

~$ sort data.txt | uniq -u
Level 9: 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM

# Level 9

The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.

`strings data.txt | grep "=\+"

lvl 10: FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey


# Level 10

The password for the next level is stored in the file **data.txt**, which contains base64 encoded data

## Commands you may need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd


~$ base64 -d data.txt

lvl 11: dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr


# Level 11

The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

~$ cat data.txt | tr '[a-z]' '[n-za-m]' | tr '[A-Z]' '[N-ZA-M]'
- [n-za-m] tells the string to rotate 13 times, or start in the 13th space?

lvl 12: The password is 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4

# Level 12

The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “mktemp -d”. Then copy the datafile using cp, and rename it using mv (read the manpages!)

## Commands you may need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd, mkdir, cp, mv, file

~$ mktemp -d
*Created a temp directory*

~$ mkdir /tmp/*temp directory*/output
*Notice how I wrote output and not output.txt*

~$ xxd -r data.txt > /tmp/*temp directory*/output

~$ file output
*Tells me which compression tool was used.

From here it's compressed in so many different formats
- gzip
- tar
- bzip2

some point I used tar xvf

I kept having to rename the file, to add an extension with the format of the tool that was used to compressed it
Ex: from output to output.gz

lvl 13:  FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn



# Level 13


















