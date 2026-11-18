## Exercise 1 - Viewing and modifying file access permissions
# 1.1 View file access permissions
>> cd /home/project
>> wget https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-LX0117EN-SkillsNetwork/labs/module%201/usdoi.txt

# Each file and each directory in your Linux system has permissions set for three permission categories: the 'user', the 'group', and 'all users' (or 'other').

# The following permissions are set for each file and directory:

>> Permission	Symbol
>> read	           r
>> write	       w
>> execute	       x

# To see the permissions currently set for a file, run the ls command with the -l option.
>> ls -l usdoi.txt

# The permissions set here are rw-r--r--. The - preceeding these permissions indicates that usdoi.txt is a file. If it were a directory, you would see a d instead of the -
# The first three entries correspond to the current user, the next three correspond to the group, and the last three are for all others. 
# No users have execute permission, as indicated by the - instead of an x in the third position for each user category.

# 1.2 Change file access permissions
# The chmod or change mode command lets you change the permissions set for a file
>> chmod

# Specify which permissions to change with a combination of the following characters:
Option	    Description
r, w, x	    Permissions: read, write, and execute
u, g, o	    User categories: user, group, and all others
+, -	    Operations: grant and revoke

# The following command revokes read permissions for all users (user, group, and other) on the file usdoi.txt
>> chmod -r usdoi.txt

# You can verify the changed permissions by entering:
>> ls -l usdoi.txt

# To grant read access to all users on usdoi.txt, enter:
>> chmod +r usdoi.txt

# Verify the changed permissions again with the following:
>> ls -l usdoi.txt

# Now to remove the read permission only for 'other' category, enter the following
>> chmod o-r usdoi.txt

## Exercise 2 - Understanding directory access permissions
# 2.1 View default directory access permissions

# Directory Permission	Permissible action(s)
>> r	list directory contents using ls command
>> w	add/remove files or directories from directory
>> x	enter directory using cd command

>> cd /home/project
>> mkdir test

# Check the default permissions that the system sets for your new test directory:
>> ls -l

> 'You, "theia", as the owner of test, have read, write, and execute permissions set by default. But all others only have read and execute permissions set and cannot write to your test directory. This means users outside your group can't add or remove files from test. They can, however, explore your directory to see what files and directories exist there.'

> Linux permissions: SUID, SGID, and sticky bit: https://www.redhat.com/sysadmin/suid-sgid-sticky-bit#:~:text=Commonly%20noted%20as%20SUID%2C%20the,use%20an%20uppercase%20S%20here.

> 'Note: You might be wondering what that s permission is in the execute slot for your group. The s stands for "special permission". It means that any new files created within the directory will have their group ownership set to be the same as the directory owner. We won't go into this level of detail in this course, but you can learn more about advanced Linux permissions here:'

# 2.2 Remove user execute permissions on your test directory
>> cd test
>> mkdir test2
>> cd ../

# Remove your user execute permissions on test using the following command
>> chmod u-x test

# Now, what happens when you try to change directories to test? >> You get an error message!
>> cd test 
>> OUTPUT: bash: cd: test: Permission denied

> NOTE: As you just removed execute permissions for yourself on your test directory, you can no longer make it your present working directory. However, you can still "read" it with the ls command

>> ls -l 

> NOTE: Even though you have "write" permissions set, you can't actually create a new directory within test, because removing execute permissions overrides write permissions. For example, entering,
>> mkdir test/test3

# throws an error:

> OUTPUT: mkdir cannot create directory ‘test/test’: Permission denied

> NOTE: This time, try restoring execute permissions on test and denying write permissions. Then verify your changes:

>> chmod u+w test
>> chmod u-w test
>> ls -l

# Now you can go into test, but you still can't write to it! Entering
>> cd test
>> mkdir test_again

# throws the error:

> mkdir: cannot create directory ‘test_again’: Permission denied






