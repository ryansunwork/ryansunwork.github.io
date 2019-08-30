---
layout: post
title: "Unix file permissions"
date: 2019-08-29
desription: How to set and read unix file permissions
tags: academic personal aug2019
---

# Reading permissions
On a Linux system, people are associated with a file or directory through three classes: the owner, the related group, and everybody else. 

For each of these three classes, three types of permissions are defined: read (including copy), write, and execute (i.e. run the file as a program, or if it's a directory, read the list of files inside).

To see permission settings, use `ls -l` like `ls -l MYFILE`.

You will get something like `-rwxrwxrwx 1 ryansun xlin ...` where:
* The initial dash means it's a file, otherwise it will be `d` for directory.
* The first trio gives the owner permissions, a `-` in place of a letter means the owner does not have that permission. The owner is the person to the right of the number 1.
* The second trio gives the group permissions. The group name is to the right of the owner name.
* The third trio gives the permissions for everybody else.

Usually for files on a cluster that you will allow people to copy but don't want them to change, it will be something like `-rwxr--r--`.

If the directory does not grant you execute permission, then you cannot traverse it.

An `s` in place of `x` means the setuid bit has been turned on. That means a user executing that file gets the permissions of the individual who owns the file or directory. Thus if I don't own a directory but it has the setuid bit on, then when I use plink to generate some association results inside the directory, it will let me write them there even if I don't have write access to the directory.

# Changing permissions
To change permissions you need the`chmod` command. We can think of the permission settings as a series of bits, where if you have the privilege then you get a 1 bit, and if not then you get a 0:
`rwx rwx rwx = 111 111 111`
`rw- rw- rw- = 110 110 110`
`rwx --- --- = 111 000 000`

`rwx = 111` in binary = 7
`rw- = 111` in binary = 6
`r-x = 101` in binary = 5
`r-- = 100` in binary = 4

So if we wanted to set `some_file` to have read and write permission for the owner but want to keep the file private from others, we would write `chmod 600 some_file`.

Other common settings are:
* `chmod 777 = rwxrwxrwx`  means anybody can do anything.
* `chmod 755 = rwxr-xr-x` means the owner can do anything, all others may read and execute the file. This is common for shared files.
* `chmod 700 = rwx------` means only the owner can do anything, others have no rights. Good for private files.
* `chmod 666 = rw-rw-rw-` means all may read and write the file.
* `chmod 644 = rw-r--r--` means the owner can read and write but all others can only read. A common setting for data files that all need to read but only the owner may change.
* `chmod 444 = r--r--r--` means everybody can only read. Probably good for genetic files that need to stay static.

You can change file ownership by becoming the superuser and using the `chown` command. Suppose we want to change the owner of `some_file` from "me" to "you.  Then do `sudo chown you some_file`.

To do the same for directories, do `sudo chgrp your_group some_directory`.



