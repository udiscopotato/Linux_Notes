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
