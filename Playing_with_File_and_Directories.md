## Navigating File System
For navigating between directories we need mainly three commands
### pwd (print working directory)
- pwd (shows current directory you're in)
### ls (list)
- ls (will list all files in the current directory)
- ls [directory path] (will list all files in specified directory)
- ls -l (list directory with description)
- ls -a (show hidden files)
- and many more
### cd (change directory)
- cd [directory name] (go to a specific directory)
- cd [directory path] (go to specific directory given in path)
- cd .. (go to previous directory)
### important terms
- "."  (single fullstop meaning current directory)
- ".." (double fullstop meaning previous directory)
- "~"  (this implies home directory of current user)
- "/"  (root directory of Linux)
## File or Directory Properties
In linux by running "ls -l" command we can get details about files and directories where we'll get a output like this
```javascript
drwxr-xr-x 4 bapun bapun 4096 Feb 21 09:34 labsetup
-rw-r--r-- 1 bapun bapun  778 Jun 15  2023 main.tf
lrwxrwxrwx 1  root  root    9 Feb 11 11:57 bin
```
from the output we can confirm the type of the file i.e
- "-" - regular file
- "d" - directory
- "l" - link
- "c" - special file or device file
- "s" - socket
- "p" - named pipe
- "b" - block device
other then file type we also get to know many more details like file owner, size, creation/modification time, file name, number of links, etc.
## Creating and Removing Files and Directories
We can create files in linux using 3 methods
### touch
- touch [file name]  (this will create a empty file with given name)
- touch index{1..5}.html  (this will create 5 html files)
### vi/nano 
- vi/nano [file name]  (this will create a file and start the editor or if the file already exists then it will open the file editor)
### cp (copy)
- cp [existing file name] [new file name]  (this will copy an existing file and create a replica of that file)
We can create Directory in linux using one command
### mkdir (make directory)
- mkdir [directory name]  (this commmand will create an empty directory of specified name)
- mkdir -p [dir1]/[subdir-1]/[subdir-2]  (this will create sub directories)
- mkdir -p [dir]/{dir-1,dir-2,dir-3{subdir-1,subdir-2}}  (this will create directory in herrical stucture)
TO REMOVE FILE AND DIRECTORY
### rm (remove)
- rm [file name]  (this will remove any file)
- rm *.ext  (this will remove file with specific extension)
- rmdir [directory name]  (remove empty directory)
- rm -r [directory name]  (remove non-empty directory)
## Copying and Moving
We can achive copy and move funtion in linux by using two commands i.e.
### cp (copy)
- cp [file name or path] [destination path]  (copy file to destination)
- cp -R/-r [source dir] [destination dir]  (copy an entire directory to detination)
### mv (move)
- mv [origin file path or name] [destination path]   (move file to destination)
- mv [directory original path] [new path]  (move directory to destination)
## Finding Files and Directories
We can search our files and directory using two commands i.e.
### find
- find [directory path] -name "file name"  (it'll find file if it's in the directory)
### locate
- locate [file name]  (it'll find the file in it's database and give the location)
*To use locate command user need to have "mlocate" package installed
*after installation user need to run command - updatedb to update locate's indexes
## Wild Cards
- A wildcard is a character that can be used as a substitute for any of a class character in a search.
There are many wild cards but some common ones are
    "*" - represent zero or more characters
    "?" - represent a single character
    "[]" -represent a range of characters
    "\" - escape character
    "^" - the begining of the line
    "$" - end of the line
## Links
- In Linux, a link is a reference to another file or directory1. It’s a way to give the same file multiple names and allow them to exist in two or more locations simultaneously.
- inode - Pointer or number of a file on the hard disk.
- to get inode numbers we can run command "ls -i"
There're two types of links in linux, i.e.
### SoftLink
- Link will be removed if the file is renamed or deleted.
- ln -s [original file path]  (this will crate a softlink or shortcut of the original file)
### HardLink
- Deleting, moving, renaming the original file will not affect he hard link.
- ln []
NOTE:-  we can not create link to a specific file or directory inside it's origin directory.
        Hard Link only work if both the origin and link reference directory is in same bulk device or in a same partition.
