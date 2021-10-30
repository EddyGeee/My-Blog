---
layout: post
title:  "Blog 6 - Linux Commands"
date:   2021-10-29.
categories: jekyll update
---

In today's blog, we'll give out a few simple commands for Linux that can benefit any beginner. Before we dive into commands, lets get a brief overview on Linux file system. 


In Linux, directory structure starts with `/` symbol, which is referred as the `root` directory.

* `man hier` gives description of the filesystem hierarchy. A few examples:
    * `/` This is the root directory. This is where the whole tree starts.
    * `/bin` This directory contains executable programs which are needed in single user mode and to bring the system up or repair it.
    * `/home` On machines with home directories for users, these are usually beneath this directory.
    * `/usr` This directory is usually mounted from a separate partition. It should hold only sharable, read-only data, so that it can be mounted by various machines running Linux.
    * `/usr/bin` This is the primary directory for executable programs. 
    
<h1> only the command </h1>

* `clear` clear the terminal screen
* `top` display Linux processes

<h1> command with options </h1>

* `ls -l` list directory contents, use a long listing format
* `df -h` report file system disk space usage, print sizes in human readable format (e.g., 1K 234M 2G)

<h1> command with arguments </h1>

* `mkdir project` create directory named 'project' in current working directory
* `man sort` manual page for `sort` command
* `wget https://s.ntnu.no/bashguide.pdf` download file from internet

<h1> command with options and arguments </h1>

* `rm -r project` remove 'project' directory 
* `paste -sd, ip.txt` combine all lines from 'ip.txt' file to single line using `,` as delimiter
