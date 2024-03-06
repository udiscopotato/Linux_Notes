# LINUX NOTES 
These are My notes that I made during my Linux study and practice These can also be used as linux Interview questions (Made By - Subham Jena)
### 1. What's Linux ?
    - Linux is an Operating System just like Windows, MacOS which sits in the middle of your hardware and User.
      It's Open-source and free.

### 2. Unix vs Linux ?
    - Unix was first developed for multiuser and multitask in mid 70s.
      then born Linux in 1991 by "Linus Trovalds" It's totally free and Open-source.
      There's some linux distribution like RedHat which is not free or user have to pay for their service.
      Nowdays linux is used by many developer community and Companies.
      Unix comparatively supports very few file systems.
      Linux can be installed on various range of devices starting from mobile, raspbary pi to super computers.
      Whereas Unix can only be installed on specific hardware.

### 3. Why there're so many flavors of Linux ?
    - Linux kernel is open-source and free to use that's why it gave developers freedom to develop their own Linux based operating system according to their need by using the linux source code that's how so many linux distos got into the market today.

### 4. Name some Linux Distros ?
    - Debian (apt package-manager) (Debian package management tool)
              Ubuntu (Debian based OS by Canonical) (apt package-manager)
                         Linux Mint (Ubuntu Based OS) (apt package-manager)
      RedHat Enterprice Linux (yum package-manger) (RPM package manager) (paid)
              Fedora (RedHat based OS) (yum) (free)
              CentOS (RedHat based OS) (yum) (free)
      Arch Linux (packman package-manager)
      Open SUSE (RPM package-manager)
      And manymore.

### 5. Linux vs Windows ?
    - Linux is free Whereas Windows is not.
      Windows is user friendly while linux is not.
      Linux is best for multitask but Windows require very high cpu, memory to perform multitask.
      Windows is mostly GUI while most linux is CLI.
      Linux is very reliable it can run months, years without reboot while windows often require reboot.
      Linux is open-source while windows is not.

### 6. What's root in Linux ?
    - Linux has a Super User account called as "root"
      root is the most powerful account that can create, modify, delete accounts and make any change to the system configuration files.

### 7. is linux case-sensitive ?
    - Linux is case-sensitive i.e. command "ABC" , "AbC" , "abc" all are different commands

### 8. What's Linux kernel ?
    - Linux kernel is not an Operating System, It's a small software within Linux OS which takes command from user and pass it to system hardware or paripherals.

### 9. What's file system and give example of some linux filesystems ?
    - File system is a major component of any OS. The filesystem manages files and directory organization in the Open-source. Without a file system, file stored in the os will be a large bulk body without any indexing.
      Some linux file systems are:-
            ext4 (default FS)
            xfs
            BtrFs

### 10. Describe linux file structure and their use ?
    - /boot - Contains files that are used by boot loader (which is essential to boot the OS).
      /root - (Super User)root user's home directory. It's not same as /.
      /dev  - System Devices or peripherals driver files.(i.e. speaker, mouse, keyboard, etc)
      /etc  - (everything to configure) Configuration files.
      /bin -> /usr/bin - Everyday User Commands or binary files.
      /sbin -> /usr/sbin - System/Filesystem Commands
      /opt  - Optional add-on applications (not part of OS apps).(i.e. third party apps like Oracle, mysql, etc)
      /proc - Running Processes (Only exists in Memory)
      /lib -> /usr/lib - Library (C,Python programming library files) files needed by commands and apps. (Linux is written using C and C++)
      /temp - Directory for storing temporary files
      /home - Home directory of Regular Users
      /var  - System variables and logs.
      /run  - System deamons start early to store temporary runtime pid files.
      /mnt  - To mount external Filesystems(Ex. NFS).
      /media - For media device mounts. (i.e. CDROM, USB, etc)
      /usr  - directory in a Linux system is used for storing system-wide, read-only files.

### 11. What's the difference between find and locate ?
    - locate uses prebuild database which should be regularly updated while find iterates over a filesystem to locate files. Thus locate is faster then find, but can be inaccurate if It's database is not updated.
    To update locate's cache we need to run command "updatedb"

### 12. 
