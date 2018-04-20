
Filesystem
==========

The game includes a filesystem for each player, which acts like a hard drive for each person. The cap on the drive may change, but as of right now, it's going to stay at 16kb.

The size is obviously incredibly small, as the game is written on my laptop as of right now, and I can't accurately predict the amount of people that will sign up.

Users will not be able to upload their own files, but the plan is to create a text editor.
As you can tell, I'm horrible at naming anything, so I'll come up with a temporary name.
```
text editor
text edit
t edit
t ed
ted
```

Sounds good enough.

Filesystem Setup
----------------
When you create a server (an account), the backend stores information such as your password (not in plaintext, @T-Mobile!), your username, your ID, your IP, and so on.

It also stores that server's filesystem, and the current plan is to do it in a JSON object. I've tried XML, and it is a horrible experience, in my opinion.

Here's what your computer looks like when you initialize it:
```
/drive
	/home
	/bin
		cd.vs
		ls.vs
		rm.vs
		rmdir.vs
		mk.vs
		mkdir.vs
		ping.vs
		req.vs
		open.vs
	/sys
		boot.sys
		bootmsg.conf
		permitted
		robots
```
It's not much, but here's how most of it works.

The `/drive/` directory is your entire hard drive.

`/home/` is dedicated towards everything personal. This includes personal scripts or inforrmation or notes or whatnot.

`/bin/` is all of your scripts.
Anything called from any terminal, wherever you are in your computer, will be able to call scripts in here.
For example, calling `ls` in a terminal will first search in your `/drive/bin/` folder for a file called `ls.vs`, and if it isn't found, it'll look in your working directory for it.

`/sys/` is everything you need for the vitality of your computer.
If `boot.sys` is tampered with in any way, your computer **will not** be able to boot.

I'll add that the PSK section does **not** store any information related to your password. It's not like it matters, because anyone viewing it will most likely have used your password to gain entry.

If anything in your boot.sys file is loaded incorrectly, your computer will not boot. Until a new account is created with the same username, any attempts to login to that account will inform the user that the computer has been destroyed.

`bootmsg.conf` can be tampered with, and is displayed to anyone who connects to your machine via SSH or login.

`permitted` includes who can view your `robots` file. There's more on that in commands.md.

`robots` is displayed to anyone who tries to call a request on your machine. You must open the port they want to request on if you want them to be able to view it.












