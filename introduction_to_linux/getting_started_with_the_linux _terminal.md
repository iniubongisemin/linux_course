# Exercise 1 - Browsing Directories
ls is a special command that the shell interprets and runs as a program.
# 1.1. Viewing files in the current working directory
>> ls

# 1.2. Viewing files and directories within any directory
> SYNTAX: ls [PATH TO DIRECTORY]

Recall some of the standard subdirectories of 'slash' that you've learned about previously:

Directory	Contains
> /bin	System commands, also called binaries
> /sbin	System administration binaries
> /usr	User programs and data
> /home	Home directory
> /media	Removable media device directories

# Exercise 2 - Navigating Directories
>> cd 
Recall the symbols used to navigate to special paths:
Symbol	Stands for path to
> ~	      Home directory
> /	      Root directory
> .	      Current directory
> ..      Parent directory

# 2.1. Changing your present working directory to your home directory
>> cd ~

# 2.2. Changing your present working directory to its parent directory
To change your current working directory to the parent directory of your present working directory, enter the following command using ..:
>> cd ..

# 2.3. Changing working directory to root directory
To change your current working directory to the root directory, use the following command with the / key:
>> cd /

# 2.4. Changing your present working directory to a child directory
Assuming you are still in your root directory, use the following command to change your present working directory to the /bin directory:
>> cd /bin
NOTE: The /bin directory is called a child of the root directory, /, because it's a subdirectory within it.

# 2.5. Changing from your working directory back to your home directory
>> cd ../home/theia
OR
>> cd ~

# 2.6. Changing from your working directory to your project directory
>> cd ../project
NB: Directories that are contained within the same parent directory are called siblings.



