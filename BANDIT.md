# Bandit

This writeup details my approach to solving bandit questions and commands used. <br>
-Arnav Sahu

# I will finish the writeup by 12th, i have done the levels already
---
## Connecting to server
<b>LEVEL GOAL</b> </br>
*The goal of this level is for you to log into the game using SSH. The host to which you need to connect is bandit.labs.overthewire.org, on port 2220. The username is bandit0 and the password is bandit0. 
Once logged in, go to the Level 1 page to find out how to beat Level 1.*

**The commands I used were :-**
1. **ssh** </br>
   The ssh command is used to remotely login to a server using the following format.</br>
   `ssh <'username'.'host name'> -p <port>`</br>
   '-p' is an attribute used to specify the port.

**Process :-** </br>
I typed the following command to login to the server- </br>
`$ ssh bandit0@bandit.labs.overthewire.org -p 2220` </br>
Then I logged in using the password </br>
`bandit0`

## Level 0
<b>LEVEL GOAL</b> </br>
_The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game._

**The commands I used were :-**
1. **ls** </br>
   The ls command is used to list the contents of a directory, in this case the home directory.</br>
   `ls`

2. **cat**<br>
   The cat command prints the data present in files of two types - text files and certain compatible binary files.<br>
   `cat filename`

**Process :-** </br>
I typed ls first to get the list of files in the home directory.<br>
`ls`<br>
Then I used cat to read the only file present 'readme'<br>
`cat readme`<br>
This gave me the password for the next level<br>
<u>**`NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL`**</u>

## Level 1
<b>LEVEL GOAL</b> </br>
*The password for the next level is stored in a file called - located in the home directory.*<br>

**Process :-** </br>
I used ls and got `-` as the only file present.<br>
`ls`<br>
Then I used cat with an an escape character `./` since normally `-` is used to signify an option for a command.<br>
`cat ./-`<br>
This gave me the passowrd for the next level<br>
<u>**`rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi`**</u>

## Level 2
<b>LEVEL GOAL</b> </br>
*The password for the next level is stored in a file called spaces in this filename located in the home directory*

**Process :-** </br>
I typed ls and got _spaces in this filename_ as a file.<br>
`ls`<br>
I used cat but used this format `"filename"` to indicate the entire group of words as one file name.<br>
`cat "spaces in this filename"`<br>
This gave me the passowrd for the next level<br>
<u>**`aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG`**</u>

## Level 3
<b>LEVEL GOAL</b> </br>
*The password for the next level is stored in a hidden file in the inhere directory.*

**The commands I used were :-**
1. **cd** </br>
   The cd command is used to change directory to any directory present in the current directory or deeper.<br>
   `cd filename`

**Process :-** </br>
I used ls and got a directory named *inhere*.<br>
`ls`<br>
Then I used cd to change directory to the *inhere* directory.<br>
`cd inhere`<br>
Then I used ls again with the `-a` option without which the ls command would not display hidden files. <br>
`ls -a`<br>
Then I used cat similar to previous levels.<br>
`cat .hidden`<br>
This gave me the passowrd for the next level<br>
<u>**`2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe`**</u>

## Level 4
<b>LEVEL GOAL</b> </br>
_The password for the next level is stored in the only human-readable file in the inhere directory._

**The commands I used were :-**
1. **file** </br>
   The file command is used to get the file type.<br>
   `file filename`

2. **find** <br>
   The find command is used to find files that fulfil specified conditions.<br>
   `find`

**Process :-** </br>
I used ls and got a directory named *inhere*.<br>
`ls`<br>
Then I used cd to change directory to the *inhere* directory.<br>
`cd inhere`<br>
Then I used ls again with `-a` just in case.<br>
`ls -a`<br>
I got multiple files in return.<br>
So I had two options:-<br>

1. Using file command since the files have very similar names with the format _-file00_ to _-file09_ and there are not too many files. This gives me the data type of each file present in the directory.<br>
`file ./-file**`<br>
The `*` indicating a variable character so any file that has a filename starting with *-file* and having any two characters will be considered by the file command, and filetype of each valid filename (all of the files in this case) will be displayed.<br>
*-file07* had filetype ASCII which is the only human-readable filetype out of the displayed filetypes.<br>
Then I used cat.<br>
`cat ./-file07`<br>
Which gave the password for the next level<br>
<u>**`lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR`**</u>

2. Using find command to search the directory for files that are human readable.<br>
`find -readable`
Which gave me *-file07*.<br>
Then I used cat.<br>
`cat ./-file07`<br>
Which gave the password for the next level<br>
<u>**`lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR`**</u>

## Level 5
<b>LEVEL GOAL</b> </br>
_The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:<br>
human-readable<br>
1033 bytes in size<br>
not executable_

**Process :-** </br>
I used ls and got a directory named *inhere*.<br>
`ls`<br>
Then I used cd to change directory to the *inhere* directory.<br>
`cd inhere`<br>
Then I used ls again with `-a` and `-l`, which shows the total no. of files including inside sub-directories<br>
`ls -l -a`<br>
Then I used find with the conditions given in the level goal.<br>
`find . -readable -size 1033c ! -executable`<br>
This gave me *./maybehere07/.file2*<br>
Then I used cat.<br>
`cat ./maybehere07/.file2`<br>
This gave me the password for the next level.<br>
<u>**`P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU`**</u>

## Level 6
<b>LEVEL GOAL</b> </br>
_The password for the next level is stored somewhere on the server and has all of the following properties:<br>
owned by user bandit7<br>
owned by group bandit6<br>
33 bytes in size_

**Process :-** </br>
The ls command did not give me any suitable file, only 3 hidden files were present and none were valid.<br>
`ls -a -l`<br>
So I directly tried the find command starting the search from the root directory.<br>
`find / -group bandit6 -user bandit7 size 33c`<br>
This gave me a list of many files, all of which were files the find command coulnt access due to lack of permission. I got the file _/var/lib/dpkg/info/bandit7.password_.<br>
Then i used cat.<br>
`cat /var/lib/dpkg/info/bandit7.password`<br>
Which gave me the password for the next level.<br>
<u>**`z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S`**</u>

## Level 7
<b>LEVEL GOAL</b> </br>
_The password for the next level is stored in the file data.txt next to the word millionth_

**The commands I used were :-**
1. **grep** </br>
The grep command is used to find patterns in a given file.
`grep 'pattern' filename`

**Process :-** </br>
ls gave one file _data.txt_<br>
`ls`<br>
Then I used grep to find tge line containing the word _millionth_<br>
`grep 'millionth' data.txt`<br>
This gave me the following output<br>
`millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP`<br>
The password being<br>
<u>**`TESKZC0XvTetK0S9xNwm25STk5iWrBvP`**</u>

## Level 8
<b>LEVEL GOAL</b> </br>
_


EN632PlfYiZbn3PhVK3XOGSlNInNE00t

