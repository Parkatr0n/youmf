
Commands
========

"Youmf" follows a unix-like command system. I've made some minor changes to make it easier on me and the client, but you can expect almost everything to be the same, sans some flags and arguments.

Filesystem
==========

cd <directory>
--
Change working directory (wdir) to the directory asked by the client.

| Arguments |                              |
|:---------:|:----------------------------:|
| directory | where you want to point wdir |

```
Park@147.252.27.79:/drive/$ cd sys
Park@147.252.27.79:/drive/sys/$ 
```

ls
--
List all current files and folders in the working directory. The output is colored: blue is a folder, and gray is a file.

No arguments or flags.

```
Park@147.252.27.79:/drive/$ ls
home
bin
sys
Park@147.252.27.79:/drive/$ 
```

rm <file>
--
Delete the specified file. This cannot be undone.

| Arguments |                         |
|:---------:|:-----------------------:|
| file      | file you want to remove |
| -r        | remove directories      |

```
Park@147.252.27.79:/drive/home/$ rm test.vs
Park@147.252.27.79:/drive/home/$ 
```

rmdir <directory>
--
Delete the specified directory, and everything inside of it. This cannot be undone.

| Arguments |                              |
|:---------:|:----------------------------:|
| directory | directory you want to remove |

```
Park@147.252.27.79:/drive/home/$ rmdir HorsePorn
Park@147.252.27.79:/drive/home/$ 
```

mk <file>
--
Create an empty file with the specified name.

| Arguments |                        |
|:---------:|:----------------------:|
| filename  | name of file to create |

```
Park@147.252.27.79:/drive/home/$ mk test.vs
Park@147.252.27.79:/drive/home/$ 
```

mkdir <directory>
--
Create a directory with the specified name.

| Arguments |                             |
|:---------:|:---------------------------:|
| directory | name of directory to create |

```
Park@147.252.27.79:/drive/home/$ mkdir Homework
Park@147.252.27.79:/drive/home/$
```

Networking
==========

ssh <target>
--------
Secure shell. Opens a terminal on the specified computer with root access to the filesystem.

The target is <user>@<ip>. The user must be the correct user assigned to that IP address.

| Arguments |                       |
|:---------:|:---------------------:|
| target    | ssh target. $user@$ip |

```
Park@147.252.27.79:/drive/home/$ ssh unhackable@69.146.24.180
unhackable@69.149.24.180's password: 
Unhackable's PC. I'm sorry if I hacked your machine it's just a gmae plz dont do anything 
unhackable@69.149.24.180:/drive/$ rm -r /drive/
```



