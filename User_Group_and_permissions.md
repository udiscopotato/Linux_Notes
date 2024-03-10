## Permissions
Linux is a multi-user system. Every files and directories can be protected from or made accesible to other users by changing it' access permissions. 
Permission to a file or directory can restricted by 3 types:
1. read(r) value = 4
2. write(w) value = 2
3. execute(x) value = 1
Each permissions can be restricted by 3 Levels:
1. user(u) = yourself or file/dir owner
2. group(g) = can be people on same project or some individuals
3. others(o) = everyone on the system
File or Directory permissions can be displayed by using "ls -l" command
Example:
    ```javascript
    drwxr-xr-x 4 bapun bapun 4096 Feb 21 09:34 labsetup
    -rw-r--r-- 1 bapun  devs  778 Jun 15  2023 main.tf
    ```
In this example first file is a directory and accesible to "bapun" user and to "bapun" group
user have all 3 permissions while groups have only read and execute permission.
in second file It's accesible to "bapun" user and "devs" group. and group have only read permisson.

To change permission of a file or directory we can use:
### chmod (change mode)
- chmod u+rw,g+r file.txt  (this command will give read and write permission to user and read to group)
- chmod a+wr  (this will give read and write permmision to all)
- chmod a-wrx  (this will remove all permissions for all)
- chmod 700  (user have all permissions 4(read)+2(write)+1(execute))
- chmod 660 directory/   (this will remove execute permmision to directory i.e. no one can cd into that directory)

### NOTE - directory having execute(x) permission implies that permited user can "cd" into that directory. If a directory doesn't have execute(x) permission, user can not go into that directory.
## Ownerships
There are two owner of a file or directory
1. User
2. Group
We can change ownership of a file using these two commands
### chown (Change Owner)
- chown root/user [file name]  (this command will change ownership of the file to specified user.)
- chown root/user [dir name]  (this command will change ownership of the directory to specified)
- chown username:groupname [file/dir] (this will change user and group owner of the specified)
### chgrp (Change Group)
- chgrp groupname [file/dir]  (change group ownership of a file)
- chgrp -R group1 group2  (It'll change the group to group2 from group1 -R is for directory)
## Access Control List (ACL permissions)
ACL provides an additional, more flexible permission mechanism for file systems. It is designed to assist with UNIX file permissions. ACL allows you to give permissions to any group any user and to any disc resource.
### Use of ACL
Imagine a scenario you want to give permmision to a perticular user who is not in the owner group.but still you want to give him read write permission without adding him to the group. here comes the use of ACL.
ACLs are used to make a flexible permission mechanism in linux.
Commands to assign or remove ACL permissions are:
### setfacl (Set File Access Control List)
- setfacl -m u:username:wrx /path/to/file  (set permission for a user)
- setfacl -m g:groupname:wr /path/to/file  (set permission for a group)
- setfacl -Rm "user or group" /path/to/dir  (set permissionn for a directory)
- setfacl -x u:username /path/to/file   (remove user access to a file)
- setfacl -b /path/to/file (to remove all users)
NOTE: setting write(w) permission with ACL doesnot allow to remove it.
### getfacl (Get File Access Control List)
- getfacl /path/to/file
- getfacl /path/to/dir
## User Management
To create user, delete user, modify user configurations we need below commands
### useradd OR adduser
- adduser username (create user in interactive way)
- useradd username (create simple user with no other specification)
- useradd -g groupname -s /bin/bash -c "Comment" -m -d /path/to/home username  (create user with given specifications NB here -m is creating home dir during user creation)
### usermod
- usermod -a -G groupname username  (to add user to group)
### userdel
- userdel username (to delete user  * this command will not remove user home dir)
- userdel -r username  (this will remove user and it's home directory)
### passwd
- passwd username  (to change password of user)
### id
- id username  (It'll show you userid with other informations)
### NOTE: 1. all user informations are present in /etc/passwd while all passwords in /etc/shadow
###       2. to login to a user we can use commmand "su - username"
###       3. a user can be part of multiple groups or can be in no groups.
## Group Management
We can achive group management using below commands
### groupadd
- groupadd groupname
### groupmod 
### groupdel
### NOTE: 1. a group can be part of other groups 
###       2. groups descriptions are available at /etc/group
## Password Aging 
we can change password age using command "chage"
### chage 
- chage -m minday -M maxday -I inactiveday -E expireday username 
### we can edit file /etc/login.defs to make our default password polity for all user (Important)
## Monitor Users
### who
- who (this command will show number of users currently logged-in with their terminal id and many more)
### last
- last (this will tell every user list logged in from last time)
### w
- 
### finger
- 
### id
- 