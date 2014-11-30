---
layout: default
title: The Basics
prev: step0.html
next: step2.html
progress: 12%
---

Now that you're connected to another machine, you'll need to move around the filesystem. When you're using the Terminal, you are always "located" in some directory. By default, you start in your home directory. You can check this with the `pwd` (**p**resent **w**orking **d**irectory) command:

{% highlight sh %}
$ pwd
/home/smith22j
{% endhighlight %}


  <div class="alert alert-dismissable alert-success">
    <button type="button" class="close" data-dismiss="alert">×</button>
    <strong>What are the extra characters before the `$` prompt?</strong>


Your terminal doesn't just show the `$` character as a prompt. It should look something like this:

{% highlight sh %}
cslab-31:~ smith22j$
{% endhighlight %}

The first part (before the `:`) is the name of the machine. Immediately after the `:` is the name of the current directory, followed by your username. Even though you're in your home directory (`/home/smith22j`) the prompt displays `~`. That's because `~` is shorthand for your home directory.

To keep examples simple, this guide will just use `$` for the shell prompt, and any lines that don't start with a `$` are output from a command.


  </div>


#### Listing files

Directories contain files (and other directories), but they aren't displayed on every prompt. To see the files and directories in your current directory run the `ls` (**l**i**s**t command):

{% highlight sh %}
$ ls
Desktop     Library   Pictures
Documents   Movies    Public
Downloads   Music     Sites
{% endhighlight %}

#### Moving around

Let's move to the `Sites` directory. You can do this with the `cd` (**c**hange **d**irectory) command:

{% highlight sh %}
$ cd Sites
{% endhighlight %}

If you want to see what's in the `Sites` directory, you'll have to run `ls` again:

{% highlight sh %}
$ ls
cs101    cs201
$ pwd
/home/smith22j/Sites
{% endhighlight %}

To move into the `cs201` directory, just run `cd` again:

{% highlight sh %}
$ cd cs201
{% endhighlight %}

#### Going back home

No matter where you are, you can just run `cd` with no argument to go back to your home directory:

{% highlight sh %}
$ cd
$ pwd
/home/smith22j
{% endhighlight %}

#### Moving around *faster*

You can move more than one directory at a time, and you don't have to type the full names of directories. If you type in...

{% highlight sh %}
$ cd Si
{% endhighlight %}

... then press <kbd>tab</kbd>, the shell will finish typing in `Sites/`. **You'll have to type an uppercase 'S' for tab completion to work.**

Don't run the command yet. We're going to move multiple directories in one step. Type `c` and push <kbd>tab</kbd> again. The shell will add an `s`, but it hasn't completed the entire directory because there are multiple options. If you hit <kbd>tab</kbd> **twice more** the shell will print the options:

{% highlight sh %}
$ cd Sites/cs
cs101/ cs201/
{% endhighlight %}

Just type the next character that distinguishes the two options (a `2`) then press <kbd>tab</kbd> one last time to finish the completion.

<strong>Run the completed command to move to your `Sites/cs201` directory and move on to the next step.</strong>
