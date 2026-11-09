# Exercise 1 - Informational Commands
# Display the name of the current user
# 1.1. Display the name of the current user
>> whoami

# 1.2. Get basic information about the operating system
By default the command prints the kernel name. The u in uname refers to "unix-like 0S".
>> uname

Using the -a option prints all the system information.
>> uname -a 

# 1.3. Obtain the user and group identity information
This command displays the user id and group id information of the current user.
>> id

# 1.4 Get available disk space
>> df
This command will display available disk space in 512-byte blocks. To get available disk space in a "human-readable" format, enter:
>> df -h

# 1.5. View currently running processes
The ps command lists each process that is currently running and its PID (process id).
>> ps

By using the -e option, you can display all of the processes running on the system. The includes processes owned by other users.
>> ps -e

# 1.6. Get information on the running processes and system resources
>> top

If you want to exit automatically after a specified number of repetitions e.g 10, use the -n option as follows:
>> top -n 10

You can press the following keys with Shift while top is running to sort the table:

Key	Sorts by
> m	Memory Usage
> p	CPU Usage
> n	Process ID (PID)
> t	Running Time

# 1.7. Display Messages
>> echo
e.g 
>> echo "Welcome to the linux lab"

These special characters help you better format your output:

Special Character	Effect
    \n	       Start a new line
    \t	       Insert a tab

Use the -e option of the echo command when working with special characters. For example:
>> echo -e "This will be printed \nin two lines"

# 1.8. Display date and time
>> date

Here are some popular format specifiers that you can try out:

Specifier	Explanation
> %d	Displays the day of the month (01 to 31)
> %h	Displays the abbreviated month name (Jan to Dec)
> %m	Displays the month of year (01 to 12)
> %Y	Displays the four-digit year
> %T	Displays the time in 24 hour format as HH:MM:SS
> %H	Displays the hour

# 1.9. View the Reference Manual For a Command
Scroll through the command's manual to find any info you may need. When you're done, press q to quit.
>> man ls


