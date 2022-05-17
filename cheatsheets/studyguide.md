---
Name: Frederick Paduani - Martello
Class: Cis106
Semester: Spring 2022
---
# Study Guide

# date
## Description
displays the date
## Syntax
date
## Examples
date

# uname
## Description
prints system information
## Syntax
uname (option)
## Examples
uname
Display all information
uname -a
Display Kernal version
uname -r

# du
## Description
Show disk usage of a set of files or directories
## Syntax
du (option) (file)
## Examples
Write counts for all files
du -a
Show the total 
du -c
Print in human readable formant
du -h

# free
## Description
Display amount of free and used memory in the system
## Syntax
Free (option)
## Examples
Display in bytes
free -b
display in gigabytes
free -g

# echo
## Description
displays a line of text
## Syntax
echo (option) (string)
## Examples
Standard output 
echo Hello

# apt
## Description
used for installing updating, and removing software
## Syntax
apt (option) 
## Examples
command to update ubuntu
sudo apt update; sudo apt upgrade -y

# pwd
## Description
sudo apt update; sudo apt upgrade -y
## Syntax
pwd (option)
## Examples
Current directory
Pwd

# cd
## Description
changing the current working directory 
## Syntax
cd (destination)
## Examples
change to home directory 
cd
previous directory 
cd -
Change to downloads directory from anywhere 
cd ~/Downloads

# ls
## Description
listing the content of a given directory or file
## Syntax
ls (options)
## Examples
Show present working directory
ls
list all files inside the working directory
ls -a
List all the files inside a given directory 
ls -a ~/Pictures

# tree
## Description
list contents of directories in a tree-like format
## Syntax
tree (options)
## Examples
list directories only
tree -d
Print the full path prefix for each file
tree -f

# man
## Description
Manual shows documentation that describe the commands
## Syntax
man (command)
## Examples
man ls
man tree
man date

# mkdir
## Description
Creates directories
## Syntax
mkdir + (option) + (directories)
## Examples
Make a directory
mkdir Cats

Make 2 directories
mkdir Dogs Cats

Make a parent and child directory 
mkdir -p Pets/Dogs/


# touch
## Description
Creates files
## Syntax
touch + file
## Examples
create a file called list
touch list

create many files
touch list_of_cars.txt script.py names.csv

create a file using absolute path
touch ~/Downloads/games.txt

# rm
## Description
removes files
## Syntax
rm + file
## Examples
remove a file rm list
remove all files inside a directory 
rm Downloads/games/*

remove an empty directory 
rmdir Downloads/games

Remove a non-empty directory 
rm -r Downloads/games

# cp
## Description
copies files/directors from a source to a destination
## Syntax
cp + files to copy + destination
cp -r + directory to copy + destination
## Examples
copy a file
cp Downloads/wallpapers.zip Pictures/

copy a directory using absolute path
cp -r ~/Downloads/wallpapers ~/Pictures/

copy the content of a directory to another directory 
cp Downloads/wallpapers/* ~/Pictures/

Copy multiple files in a single command
sudo cp -r script.sh program.py home.html assets/ /var/www/html/

# mv
## Description
moves and renames directories 
## Syntax
mv + source + destination
To rename
mv + file/directory to rename + new name
## Examples
from a directory to a relative path
mv Downloads/homework.pdf Documents/

Move from one directory to another using absolute path
sudo mv ~/Downloads/theme /usr/share/themes

move multiple directories/files to a different directory
mv games/ wallpapers/ rockmusic/ /media/student/flashdrive/

Rename a file 
mv homework.docx cis106homework.docx

Rename using absolute path
mv ~/Downloads/homework.docx ~/Downloads/cis106homework.docx

move and rename a file in the same command
mv Downloads/cis106homework.docx Documents/new_cis106homework.docx

# stat
## Description 
display file or system status
## Syntax
stat + option + file
## Examples
display a files inode data
stat script.sh

# Wildcards (*,?,[])
## Description
Letters and characters used to specify a file name for searches
## Syntax
*Wildcard
ls *.file type

? Wildcard 
match one character
ls + character + ?

[] Wildcard 
match a single character in range
ls +[character ]
## Examples
*
match a file ending in .txt
ls *.txt

List all files inside a directory that contain the word random
ls Downloads/ *random*

List all csv and txt files
ls Downloads/*.txt Downloads/*.csv

List all markdown files that start with the word random
ls random*.md

?
list all files that start with a . or .. and have any character after it
ls .??*

List all hidden files
ls ./.??*

List all files that have a single character between letter f and l
ls f?l*

List all files that have a 3 letter file extension 
ls *.???

[]
Match all files that have a vowel after letter f
ls f[aeiou ]*

Match all files thats name has a least one number
ls*[!0-9 ]*

Match all files whose name begins with any of these two sets of characters letters from a-f or p-z
ls [a-fp-z ]*

# Brace expansion
## Description
allows you to generate arbitrary strings to use with commands
## Syntax
command + file{character}
## Examples
To create a whole directory structure in a single command
mkdir -p music/{jazz,rock}/{mp3files,videos,oggfiles}/new{1..3}

Remove multiple files in a single directory
rm -r {dir1,dir2,dir3,fiile.txt,file,py}

To create a N number of files
touch file{A..Z}.txt
touch file{{a..z},{0..10}}.js

# cat
## Description
used for display the content of a file
## Syntax
cat + option + files to display
## Examples
Display the content of a file located in the pwd
cat todo.md

Display the content of a file using absolute path
cat ~/Documents/todo.md

Display the content of a file with line numbers
cat -n ~/Documents.todo.md

Display the content of a file with line numbers excluding empty lines
cat -b ~/Documents/todo.md

Display the content of a file a $ at the end of every line

cat -E ~/Documents/todo.md

# head
## Description
displays the top N number of lines of a given file. It prints the first 10 lines by default
## Syntax
head + option + file(s)
## Examples
Display the first 10 lines of a file
head ~/Documents/book/dracula.txt

Display the first 5 lines
head -5 ~/Documents/book/dracula.txt

# tail
## Description
Displays the last N number of lines of a give file. It prints the last 10 lines by default 
## Syntax
tail + option + file
## Examples
Display the last 10 lines of a file
tail ~/Documents/Book/dracula.txt

Displays the last 5 lines of a file
tail -5 ~/Documents/Book/dracula.txt

# cut
## Description
Used to extract a specific section of each line of a file and display it to the screen 
## Syntax
cut + option + file(s)
## Examples
Display a list of all the users in your system 
cut -d ':' -f1 /etc/passwd

Display a list of all the users in your system with their login shell
cut -d ':' -f1,7 /etc/passwd

Cut a range of bytes per line
cut -b 1-5 usernames.txt

Cut a file excluding a given field
cut -d ',' --complement -s -f3 users.txt

# tr
## Description
Used for translating or deleting characters from standard output
## Syntax
Standard output | tr + option + set + set
## Examples
Translate one character to another (For example a period with a comma)
cat file.txt | tr '.' ','

Translate white space into tabs
cat program.py | tr "[:space: ]" '\t'

Translate tabs into space
cat file.py | tr -s "[:space: ]" ' '

# paste
## Description
Joining files horizontally in columns
## Syntax
paste + option + files
## Examples
Merge two files
paste user.lst ip_address.lst

Merge two files using a different delimiter 
paste -d ":" users1.lst ip_addresses.lst

# wc
## Description
Used for printing the numbers of lines characters and bytes in a file
## Syntax
wc + option + file(s)
## Examples
Display the number of characters in a file
wc -m users.txt

Display the number of lines in a file
wc -l users.txt

Display the number words in a file 
wc -w users.txt

# grep
## Description
Used to search text in given file. Grep works line by line basis
## Syntax
grep + option + search criteria + files
## Examples
Search any line that contains the word "dracula" in the given file
grep 'dracula ~/Documents/dracula.txt

Search for a given strings inside files in a given directory
grep -iR 'conf' /etc/

Search for more than one word per line
grep -Ewn 'horror|love|scare' ~/Documents/Books/Dracula.txt

# output redirection
## Description
The pipe allows you to redirect the standard output of a command to the standard input of another
## Syntax
command_1 | command_2 | command_3 | .... | command_N
## Examples
Use grep to look for a string in a particular man page
man ls | grep "human-readable"

Display only the options of the command from its man page
man ls| grep "^[[:space: ]]*[[:punct: ]]"

Display only the 2nd line in a file
head -2 file.lst | tail -1

# Saving the output of a command
## Description

## Syntax
command output + > + file
## Examples
save the output of a command to a file
ls -lA ~ > all-files-in-home.txt

Save the error generated by a command to a file
ls -lA downloads/ 2> error-of-ls

Save the error and success to the same file
ls -lA downloads/ Pictures &> alloutput.txt

# vim or nano (basic stuff: open a file, close a file, edit a file)
## Description
Vi command-line text editor
## Syntax
## Examples
start vim
vim
Save a file
w: filename

# tar
## Description
Creates archives by combing files and directories into a single file
## Syntax
Create an archive
tar + options + archive name + files to add to archive

To extract an archive
tar + options + files to extract

## Examples
Create archive
tar -cf example.tar file1 file2 file3

extract archive 
tar -xf example.tar

Extract an specifics file 
tar -xf example.tar file3

# gz, bzip2, or xz
## Description
Compress files in place meaning the original file is deleted after compression
## Syntax
gzip + file
## Examples
Compress a single file
gzip File.txt

Compress multiple files
gzip file1.txt file2.txt file3.txt

compress files recursively
gzip -r schoolfiles

# chmod 
## Description
used to change permissions on files and directories 
## Syntax
chmod permissions file/directory
## Examples
Add execute permission to file 3
chmod u+x file3

Remove read permission for others in all 3 files
chmod o-r file{1..3}