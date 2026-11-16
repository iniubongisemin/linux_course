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
