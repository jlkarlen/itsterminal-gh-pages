---
layout: default
title: Something new
prev: step1.html
next: step3.html
progress: 23%
---

Moving around isn't the only thing you can do from a terminal. In this step you'll learn how to manipulate files and directories.

#### Manipulating directories

Before we do any more work on this lab, we should set up a directory for the lab. You can create a directory with the `mkdir` (**m**a**k**e **dir**ectory) command:

{% highlight sh %}
$ mkdir Lab 10
{% endhighlight %}

Make sure the command did what we wanted by running `ls`:

{% highlight sh %}
$ ls
10              Assignment4     Assignment8     Lab3     Lab7
Assignment1     Assignment5     Lab             Lab4     Lab8
Assignment2     Assignment6     Lab1            Lab5     Lab9
Assignment3     Assignment7     Lab2            Lab6
{% endhighlight %}

**Uh oh**. Where's the directory for lab 10?

The command above created two directories: one called `10` and one called `Lab`. That's because arguments to terminal commands are separated by spaces. No problem, we can clean up with the `rmdir` (**r**e**m**ove **dir**ectory) command and try again:

{% highlight sh %}
$ rmdir 10 Lab
$ mkdir Lab10
{% endhighlight %}

Check the result with `ls` again to make sure it worked this time. Move into the `Lab10` directory when you're done (forgot how? Try the `cd` command or take a look at the previous page).

#### Manipulating files

You can use the `mv` command to **m**o**v**e files or directories. This command will move the output of the `script` command to your lab directory:

{% highlight sh %}
$ mv ~/typescript .
{% endhighlight %}

The `mv` command just takes the first file and moves it to the second. The `.` file is just a name for the current directory. If the second location is a directory, the file will be added to the directory. If not, the first file will be renamed.

You can create an empty file with the `touch` command:

{% highlight sh %}
$ touch test
{% endhighlight %}

The above command will create a file called `test` with no contents. You can rename the file by running the command:

{% highlight sh %}
$ mv test test2
{% endhighlight %}

If you want a *copy* of the file, use the `cp` command:

{% highlight sh %}
$ cp test2 test1
$ ls
test1   test2   typescript
{% endhighlight %}

Empty files aren't all that interesting, so let's write something to them. The `echo` command takes its arguments and returns them as output:

{% highlight sh %}
$ echo hello world
hello world
{% endhighlight %}

This won't write to a file, but we can combine it with *redirection* to send the output to a file instead of the terminal. The `>` character takes the output from the command to its left and writes it to the file name on the right.

{% highlight sh %}
$ echo hello world > test3
{% endhighlight %}

Redirecting output with `>` will overwrite the existing file, or create a new one if it doesn't exist already. To append to the end of a file, redirect with `>>`.

#### Viewing files

To print the contents of a file, you can use the `cat` command (it con**cat**enates it to the terminal output):

{% highlight sh %}
$ cat test3
hello world
{% endhighlight %}

What do you think will be in the `output` file after the following commands are run?

{% highlight sh %}
$ echo hello > test1
$ echo eclipse > test2
$ echo world > test3
$ echo terminal >> test1
$ cat test1 > test3
$ echo goodbye > output
$ cat test2 >> output
$ cat test1 >> output
{% endhighlight %}

Use `echo` and `>` to write your guess to a file named `guess`. Were you right?

Some files, like your Java source code, are too long to print out on the terminal. The `less` command shows you just one page at a time. You can scroll with arrow keys, or press <kbd>q</kbd> to quit.

There are **much better** ways to edit files than with `echo`, `cat`, and redirection. We'll cover one of them on the next page.
