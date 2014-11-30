---
layout: default
title: You're done
prev: step8.html
progress: 100%
---

You've finished! That wasn't so bad, was it?

You'll need to run `exit` twice to quit cleanly: once to leave the `script` program that saved your commands, and a second time to disconnect from the remote machine.

{% highlight sh %}
$ exit
exit

Script done, output file is typescript
$ exit
logout
Connection to cslab-31.cs.mtholyoke.edu closed.
{% endhighlight %}

#### Have a Windows machine?

Unfortunately, the command line in Windows is completely different from a UNIX terminal. It's also a lot less useful than the terminal on a Mac or Linux machine. You can set up a UNIX-like environment though:

There is a package for Windows called [Cygwin](http://cygwin.com/install.html) that gives you a UNIX-style terminal on a Windows machine, including almost all of the commands we used for this lab.

You can also use [PuTTY](http://www.putty.org) on Windows to connect to a Mac or Linux machine using `ssh`. Once you're connected, everything works the way it did in this lab.
