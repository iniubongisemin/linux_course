## Exercise 1 - Navigating Files and Directories 
# 1.1. Get the location of the present working directory
>> pwd

# 1.2. List the files and directories in a directory
>> ls

# List the many binary and executable files which are present in your /bin (binaries) directory.
>> ls /bin

# The /bin directory happens to be where Linux commmands such as ls and pwd are stored. 
>> ls /bin/ls

# To list all files starting with b in the /bin directory, try entering the following:
>> ls /bin/b*

# To list all files ending in r in the /bin directory, enter the following:
>> ls /bin/*r

# To print a longer list of files with additional information, such as the last-modified date, enter the following:
>> ls -l

# Here are some common options that you can try with the ls command:
Option	Description
>> -a	    list all files, including hidden files
>> -d	    list directories only, do not include files
>> -h	    with -l and -s, print sizes like 1K, 234M, 2G
>> -l	    include attributes like permissions, owner, size, and last-modified date
>> -S	    sort by file size, largest first
>> -t	    sort by last-modified date, newest first
>> -r	    reverse the sort order

# To get a long list of all files in /etc, including any hidden files, enter the following:
>> ls -ls /etc

## Exercise 2 - Creating Files and Directories
# 2.1. Create a directory
>> mkdir scripts

# 2.2. Change your current working directory
>> cd scripts

# The syntax .. is a shortcut that refers to the parent directory of your current directory. 
>> cd ..

# 2.3. Create an empty file
>> touch

# Create an empty file named myfile.txt
>> touch myfile.txt

# And use the date command to verify the date change
>> date -r myfile.txt

## Exercise 3 - Managing Files and Directories
# 3.1. Search for and locate files

