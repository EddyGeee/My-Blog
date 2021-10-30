---
layout: post
title:  "Blog 6 - Linux Commands"
date:   2021-10-29.
categories: jekyll update
---

Before we dive into ocean of commands, lets get a brief on Linux file system. If you've used Windows, you would be familiar with `C:` `D:` etc.  
In Linux, directory structure starts with `/` symbol, which is referred as the `root` directory

* `man hier` gives description of the filesystem hierarchy. A few examples:
    * `/` This is the root directory. This is where the whole tree starts.
    * `/bin` This directory contains executable programs which are needed in single user mode and to bring the system up or repair it.
    * `/home` On machines with home directories for users, these are usually beneath this directory, directly or not. The structure of this directory depends on local administration decisions.
    * `/tmp` This directory contains temporary files which may be deleted with no notice, such as by a regular job or at system boot up.
    * `/usr` This directory is usually mounted from a separate partition. It should hold only sharable, read-only data, so that it can be mounted by various machines running Linux.
    * `/usr/bin` This is the primary directory for executable programs. Most programs executed by normal users which are not needed for booting or for repairing the system and which are not installed locally should be placed in this directory.
    * `/usr/share` This directory contains subdirectories with specific application data, that can be shared among different architectures of the same OS. Often one finds stuff here that used to live in /usr/doc or /usr/lib or /usr/man.
