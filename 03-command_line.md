# Learn command line

Please follow and complete the free online [Bash Scripting Tutorial](https://ryanstutorials.net/bash-scripting-tutorial/) or [Codecademy's Learn the Command Line](https://www.codecademy.com/learn/learn-the-command-line). These are helpful tutorials. You should be able to go through these in a couple of hours.

**Note:** Bash is not installed on a PC. Rather, PC users must install Cygwin. Once Cygwin has been installed, the command line interface witll _emulate_ bash. You can find all information regarding Cygwin [here](https://www.cygwin.com/).

---

### Q1.  Cheat Sheet of Commands  

Here's a list of items with which you should be familiar:  
* show current working directory path
* creating a directory
* deleting a directory
* creating a file using `touch` command
* deleting a file
* renaming a file
* listing hidden files
* copying a file from one directory to another

Make a cheat sheet for yourself: a list of at least **ten** commands and what they do.  (Use the 8 items above and add a couple of your own.)  

> > REPLACE THIS TEXT WITH YOUR RESPONSE

pwd :show current working directory path
mkdir [dir] :create a directory
rm -R [dir] :delete directory and files
rmdir [dir] :delete empty directory
touch [file] :create a file
rm [file] :delete a file
mv [file] [newfile] :rename a file
ls -a :list hidden files in directory
cp [file] [dir] :copye a file to another directory
cd [dir] : change directory
sudo [command] : run command with security privileges of the superuser
clear :clears the screen
grep [search_pattern] [file] :search for all lines that contain the pattern

### Q2.  List Files in Unix   

What do the following commands do:  
`ls`  
`ls -a`  
`ls -l`
`ls -lh`  
`ls -lah`  
`ls -t`  
`ls -Glp`  

`ls`  :list directory contents
`ls -a`  :list files including hidden files starting with '.'
`ls -l`  :list files in long format, showing permissions
`ls -lh`  :list files in ling format with readable file size
`ls -lah`  :list all files including hidden files in long format with human readable sizes
`ls -t`  :list files sorted by time and date
`ls -Glp`  :list files in long format without group names and '/' appended to directories

---

### Q3.  More List Files in Unix  

Explore these other [ls options](http://www.techonthenet.com/unix/basic/ls.php) and pick 5 of your favorites:

`ls -c`  :Displays files by file timestamp
`ls -d`  :Displays only directories
`ls -m`  :Displays the names as a comma-separated list
`ls -R`  :Displays subdirectories as well
`ls -u`  :Displays files by the file access time

---

### Q4.  Xargs   

What does `xargs` do? Give an example of how to use it.

xargs is a command that allows you to convert standard input into arguments for a command. For example, if we wanted to create three python files for parts 1, 2 and 3 of a project, we could use the following command:

printf 'part_1\part_2\part_3\' | xargs -i touch {}.py



