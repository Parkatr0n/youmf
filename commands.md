
Commands
========

"Youmf" follows a unix-like command system. I've made some minor changes to make it easier on me and the client, but you can expect almost everything to be the same, sans some flags and arguments.

The end goal (hopefully) is to have each command be written using VS and be stored in the /drive/bin/ folder, rather than using pure JS to work with information.

I'd like to add that the only command that will not be written in VS is `signup`, and that's for obvious interception and encryption reasons.

Filesystem
==========

cd directory
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

rm file
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

rmdir directory
--
Delete the specified directory, and everything inside of it. This cannot be undone.

| Arguments |                              |
|:---------:|:----------------------------:|
| directory | directory you want to remove |

```
Park@147.252.27.79:/drive/home/$ rmdir HorsePorn
Park@147.252.27.79:/drive/home/$ 
```

mk file
-------
Create an empty file with the specified name.

| Arguments |                        |
|:---------:|:----------------------:|
| filename  | name of file to create |

```
Park@147.252.27.79:/drive/home/$ mk test.vs
Park@147.252.27.79:/drive/home/$ 
```

mkdir directory
---------------
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

ssh target
----------
Secure shell. Opens a terminal on the specified computer with root access to the filesystem.

The target is `user@ip`. The `user` must be the correct username assigned to that IP address.

| Arguments |                           |
|:---------:|:-------------------------:|
| target    | ssh target. `username@ip` |

```
Park@147.252.27.79:/drive/home/$ ssh unhackable@69.146.24.180
unhackable@69.149.24.180's password: 
Unhackable's PC. I'm sorry if I hacked your machine it's just a gmae plz dont do anything 
unhackable@69.149.24.180:/drive/$ rm -r /drive/
```

ping target
-----------
Sends 8 requests to the target with random 8 byte strings in each packet. Here's an example of one packet:
```
rk0GsyMg
```
In total, one `ping` will transmit 64 bytes of information.

| Arguments |                                  |
|:---------:|:--------------------------------:|
| target    | ping target, standard ip address |

```
Park@147.252.27.79:/drive/home/$ ping 69.146.24.180
1. Sending...Response (4ms)
2. Sending...Response (3ms)
3. Sending...Response (2ms)
4. Sending...Response (3ms)
5. Sending...Response (2ms)
6. Sending...Response (2ms)
7. Sending...Response (1ms)
8. Sending...Response (2ms)
Park@147.252.27.79:/drive/home/$
```

req target:port
---------------
This is a possible feature. Send a request to a computer on the given port. The request will ask for the information from their `robots` file (stored in /drive/sys/), and send it back to the user.

If no port is specified, then HTTP (80) will be used.

The port must be open on the target computer to fetch the file.

| Arguments |                               |
|:---------:|:-----------------------------:|
| target    | request target, `target:port` |

The following code requests `robots` from `69.146.24.180` on port 216, and returns it to the user.
```
Park@147.252.27.79:/drive/$ req 69.146.24.180:80

Hello! I'm unhackable. You might know me as... unhackable! ahahahaha You can't hack me. Cya.
Park@147.252.27.79:/drive/$ 
```

open port
---------
This is a possible feature. Opens port `port` on the user's computer to everyone.

I plan to add a `permitted` file in /drive/sys/, which specifies which hosts are allowed to connect on what ports.
Here's what it would look like:
```
# /drive/sys/permitted
# ip:port
# Adding an IP and a port to this list means that that IP will be able to connect to your machine using that port.

25.62.135.125:216
15.153.25.195:80
159.122.85.210:80
117.91.159.28:443
```

| Arguments |                                |
|:---------:|:------------------------------:|
| port      | port number to open. (1-65535) |

The below code opens port 80 on Park's computer, meaning anyone can connect and view `robots`.

```
Park@147.252.27.79:/drive/$ open 80
Park@147.252.27.79:/drive/$
```











