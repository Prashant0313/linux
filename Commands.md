`df` : To see the current amount of free space on our disk drives.

	──(kali㉿kali)-[~]
	└─$ df        
	Filesystem     1K-blocks     Used Available Use% Mounted on
	udev              956796        0    956796   0% /dev
	tmpfs             200472     1296    199176   1% /run
	/dev/sda2       39554360 18474188  19038728  50% /
	tmpfs            1002348        0   1002348   0% /dev/shm
	efivarfs             256      126       126  50% /sys/firmware/efi/efivars
	tmpfs               5120        0      5120   0% /run/lock
	tmpfs               1024        0      1024   0% /run/credentials/systemd-journald.service
	tmpfs            1002348        0   1002348   0% /tmp
	/dev/sda1         523244      148    523096   1% /boot/efi
	tmpfs             200468      124    200344   1% /run/user/130
	tmpfs             200468      144    200324   1% /run/user/1000

to display the amount of free memory, enter the free command.
`──(kali㉿kali)-[~]
`└─$ free`            
	          total             used        free            shared     buff/cache   available
Mem:         2004696      998484      598592       17332      570532       1006212
Swap:         999420           0      999420


`ls` To list the files and directories in the current working directory, we use the ls command.
![[/images/Pasted image 20250503214856.png]]

![[/images/Pasted image 20250505181518.png]]
we will use the file command to determine a file’s type.
	`──(kali㉿kali)-[~]
	`└─$ file`    *filename*

The less command is a program to view text files.
	`──(kali㉿kali)-[~]
	`└─$ less`    *filename*
![[/images/Pasted image 20250505182207.png]]

| Directory      | Comments                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| /              | The root directory, where everything begins.                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| /bin           | Contains binaries (programs) that must be present for the system to boot and run.                                                                                                                                                                                                                                                                                                                                                                                                                 |
| /boot          | Contains the Linux kernel, initial RAM disk image (for drivers needed at boot time), and the boot loader. Interesting files include /boot/ grub/grub.conf, or menu.lst, which is used to configure the boot loader, and /boot/vmlinuz (or something similar), the Linux kernel.                                                                                                                                                                                                                   |
| /dev           | This is a special directory that contains device nodes. “Everything is a file” also applies to devices. Here is where the kernel maintains a list of all the devices it understands.                                                                                                                                                                                                                                                                                                              |
| /etc           | The /etc directory contains all the system-wide configuration files. It also contains a collection of shell scripts that start each of the system services at boot time. Everything in this directory should be readable text. While everything in /etc is interesting, here are some all-time favorites: /etc/crontab, a file that defines when automated jobs will run; /etc/fstab, a table of storage devices and their associated mount points; and /etc/passwd, a list of the user accounts. |
| /home          | In normal configurations, each user is given a directory in /home. Ordinary users can write files only in their home directories. This limi tation protects the system from errant user activity.                                                                                                                                                                                                                                                                                                 |
| /lib           | Contains shared library files used by the core system programs. These are similar to dynamic link libraries (DLLs) in Windows.                                                                                                                                                                                                                                                                                                                                                                    |
| /lost+found    | Each formatted partition or device using a Linux file system, such as ext3, will have this directory. It is used in the case of a partial recov ery from a file system corruption event. Unless something really bad has happened to your system, this directory will remain empty.                                                                                                                                                                                                               |
| /media         | On modern Linux systems, the /media directory will contain the mount points for removable media such as USB drives, CD-ROMs, and so on, that are mounted automatically at insertion.                                                                                                                                                                                                                                                                                                              |
| /mnt           | On older Linux systems, the /mnt directory contains mount points for removable devices that have been mounted manually.                                                                                                                                                                                                                                                                                                                                                                           |
| /opt           | The /opt directory is used to install “optional” software. This is mainly used to hold commercial software products that might be installed on the system.                                                                                                                                                                                                                                                                                                                                        |
| /proc          | The /proc directory is special. It’s not a real file system in the sense of files stored on your hard drive. Rather, it is a virtual file system main tained by the Linux kernel. The “files” it contains are peepholes into the kernel itself. The files are readable and will give you a picture of how the kernel sees your computer.                                                                                                                                                          |
| /root          | This is the home directory for the root account.                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| /sbin          | This directory contains “system” binaries. These are programs that perform vital system tasks that are generally reserved for the superuser.                                                                                                                                                                                                                                                                                                                                                      |
| /tmp           | The /tmp directory is intended for the storage of temporary, transient files created by various programs. Some configurations cause this directory to be emptied each time the system is rebooted.                                                                                                                                                                                                                                                                                                |
| /usr           | The /usr directory tree is likely the largest one on a Linux system. It contains all the programs and support files used by regular users.                                                                                                                                                                                                                                                                                                                                                        |
| /usr/bin       | /usr/bin contains the executable programs installed by your Linux distribution. It is not uncommon for this directory to hold thousands of programs.                                                                                                                                                                                                                                                                                                                                              |
| /usr/lib       | The shared libraries for the programs in /usr/bin.                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| /usr/local     | The /usr/local tree is where programs that are not included with your distribution but are intended for system-wide use are installed. Programs compiled from source code are normally installed in /usr/ local/bin. On a newly installed Linux system, this tree exists, but it will be empty until the system administrator puts something in it.                                                                                                                                               |
| /usr/sbin      | Contains more system administration programs.                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| /usr/share     | /usr/share contains all the shared data used by programs in /usr/bin. This includes things such as default configuration files, icons, screen backgrounds, sound files, and so on.                                                                                                                                                                                                                                                                                                                |
| /usr/share/doc | Most packages installed on the system will include some kind of documentation. In /usr/share/doc, we will find documentation files organized by package.                                                                                                                                                                                                                                                                                                                                          |
| /var           | With the exception of /tmp and /home, the directories we have looked at so far remain relatively static; that is, their contents don’t change. The /var directory tree is where data that is likely to change is stored. Various databases, spool files, user mail, and so forth, are located here.                                                                                                                                                                                               |
| /var/log       | /var/log contains log files, records of various system activity. These are important and should be monitored from time to time. The most useful ones are /var/log/messages and /var/log/syslog. Note that for security reasons on some systems, you must be the superuser to view log files.                                                                                                                                                                                                      |

### Symbolic link and hard link

After some research on this topis 


### Wildcards
These are the special characters which used to specify the group of filenames 
![[/images/Pasted image 20250506011622.png]]
![[/images/Pasted image 20250506011707.png]]
![[/images/Pasted image 20250506011935.png]]

### mkdir—Create Directories

`mkdir` *directory...*

### cp—Copy Files and Directories

`cp` *itme1  item2*
`cp` *file...  destination*
##### Useful Options and Examples
![[/images/Pasted image 20250506012501.png]]
![[/images/Pasted image 20250506012840.png]]

### mv—Move and Rename Files

The mv command performs both file moving and file renaming, depending on how it is used. In either case, the original filename no longer exists after the operation.

`mv` *orginal_filename  changed_filename*

to move or rename the file or directory

`mv` *file ...  destination*

![[/images/Pasted image 20250506013804.png]]

### rm—Remove Files and Directories
The rm command is used to remove (delete) files and directories
`rm` *file ...*

![[/images/Pasted image 20250506014011.png]]
> Tip: whenever you use wildcards with rm (besides carefully checking your typing!), test the wildcard first with ls. This will let you see the files that will be deleted. Then press the up arrow to recall the command and replace ls with rm.

![[/images/Pasted image 20250506014532.png]]

### `type` Display a command's type

we have multiple types of commands in linux like binary executive files , shell built in command , alias and shell functions, to know the type of command we use `type` command. 
`type` *command*

### `which`—Display an Executable’s Location

To determine the exact location of a given executable, the which command is used.
`which` *ls*

### `help` Get Help for Shell Builtins 
bash has a built-in help facility available for each of the shell builtins. To use it, type help followed by the name of the shell builtin.

	[me@linuxbox ~]$ help cd 
	cd: cd [-L|[-P [-e]] [-@]] [dir] 
	Change the shell working directory.

> A note on notation: When square brackets appear in the description of a command's syntax, they indicate optional items. A vertical bar character indicates mutually exclusive items. In the case of the cd command above: cd [-L|[-P[-e]]] [dir] This notation says that the command cd may be followed optionally by either a -L or a -P and further, if the -P option is specified the -e option may also be included followed by the optional argument dir. 


### `--help` Display Usage Information
Many executable programs support a --help option that displays a description of the command's supported syntax and options.

### `man` Display a Program’s Manual Page
Most executable programs intended for command line use provide a formal piece of documentation called a *manual* or *man page*.

>The “manual” that man displays is broken into sections and covers not only user commands but also system administration commands, programming interfaces, file formats, and more. Table 5-1 describes the layout of the manual.
>Sometimes we need to refer to a specific section of the manual to find what we are looking for.

![[/images/Pasted image 20250506224044.png]]


### `apropos` Display Appropriate Commands
It is also possible to search the list of man pages for possible matches based on a search term.

### `whatis` Display One-line Manual Page Descriptions
The whatis program displays the name and a one-line description of a man page matching a specified keyword.

### Creating Our Own Commands with alias
`alias name='string'`
After the command alias, we give our alias a name followed immediately (no whitespace allowed) by an equal sign, followed immediately by a quoted string containing the meaning to be assigned to the name. After we define our alias, we can use it anywhere the shell

`me@linuxbox ~]$ alias foo='cd /usr; ls; cd -'`

To remove an alias, the `unalias` command is used, like so.

There is one tiny problem with defining aliases on the command line. They vanish when your shell session ends. to remain these alias we need to write these alias inot a .alias file 

