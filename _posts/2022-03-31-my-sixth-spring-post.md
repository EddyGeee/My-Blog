---
layout: post
title:  "Spring 22 - Blog 6"
date:   2022-03-31.
categories: Fabric Rsync SSH
---

Fabric is a high level Python module built on top of Paramiko to execute hell commands remotely over SSH. Those familiar with Paramiko are able to understand the underlying similarities between the two SSH modules. Similar to Paramiko, one can import the library into a Python script or install it directly to their Python interpreter. 

Here are some example code modules:

Run singular commands on an individual host instance <br>
    >>> result = Connection('web1').run('hostname')
        web1
        >>> result
        <Result cmd='hostname' exited=0>
Single commands across multiple hosts <br>
    >>> from fabric import SerialGroup
        >>> result = SerialGroup('web1', 'web2').run('hostname')
        web1
        web2
        >>> # Sorting for consistency...it's a dict!
        >>> sorted(result.items())
    (<Connection host=web1>, <Result cmd='hostname' exited=0>), ...]   
Here are examples covering Fabric imported into a Python script <br>
    import Fabric
    >>> def disk_free(c):
    ...     uname = c.run('uname -s', hide=True)
    ...     if 'Linux' in uname.stdout:
    ...         command = "df -h / | tail -n1 | awk '{print $5}'"
    ...         return c.run(command, hide=True).stdout.strip()
    ...     err = "No idea how to get disk space on {}!".format(uname)
    ...     raise Exit(err)
    ...
    >>> print(disk_free(Connection('web1')))
Running on multiple hosts <br>
    >>> # NOTE: Same code as above!
    >>> def disk_free(c):
    ...     uname = c.run('uname -s', hide=True)
    ...     if 'Linux' in uname.stdout:
    ...         command = "df -h / | tail -n1 | awk '{print $5}'"
    ...         return c.run(command, hide=True).stdout.strip()
    ...     err = "No idea how to get disk space on {}!".format(uname)
    ...     raise Exit(err)
    ...
    >>> for cxn in SerialGroup('web1', 'web2', 'db1'):
    ...    print("{}: {}".format(cxn, disk_free(cxn)))
    <Connection host=web1>: 33%
    <Connection host=web2>: 17%
    <Connection host=db1>: 2%
First and foremost it's important to understand the capabilities of this library. It's capable of automating and provisioning multiple instances directly from your local machine. Multiple tasks may be given in a single CLI session, through the use of `fab build deploy`. Just setup a `fabfile` and setup hostname initialization to connect to your servers/instances. 


