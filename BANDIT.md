# Bandit

This writeup details my approach to solving bandit questions and commands used.
---
## Level 0
*<b>LEVEL GOAL</b> </br>
The goal of this level is for you to log into the game using SSH. The host to which you need to connect is bandit.labs.overthewire.org, on port 2220. The username is bandit0 and the password is bandit0. 
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

## Level 1
*<b>LEVEL GOAL</b> </br>
_The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game._

**The commands I used were :-**
1. **ls** </br>
  The ls command is used to list the contents of a directory, in this case the home directory.

   NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

   rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU


