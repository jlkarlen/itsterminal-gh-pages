---
layout: default
title: Searching and combining commands
prev: step5.html
next: step7.html
progress: 67%
---

#### Searching

You can search for files by name using the `find` command. This command takes in search options, followed by a directory to start the search. This command will search for Java files inside the `src` directory or one of its subdirectories:

{% highlight sh %}
$ find src -name "*.java"
{% endhighlight %}

If you only want to show files modified in the last five days, you can add the flag `-mtime 5` flag:

{% highlight sh %}
$ find src -name "*.java" -mtime 5
{% endhighlight %}

You can also search *inside* files with the `grep` command. This command only looks in the local directory by default, but the `-R` flag will cause it to search inside subdirectories as well. This command will search for files that contain the keyword "Stack" inside the `src` directory:

{% highlight sh %}
$ grep -R Stack src
{% endhighlight %}

#### Combining commands

Redirection (from [step 2](step2.html)) saves a command's output to a file. Sometimes, you actually want to use a command's output as part of another command.

If you surround a command in backticks ("\`", the same key as "~"), the command will run and its output will be "pasted" into the outer command. For example, this command lists all the Java files in your `src` directory:

{% highlight sh %}
$ find src -name "*.java"
{% endhighlight %}

You can pass this list of files to `javac` using backticks:
{% highlight sh %}
$ javac -d bin `find src -name "*.java"`
{% endhighlight %}

You can also pass the output of one command as input to the next using `|` (called "pipe", on the same key as `\`). Commands that typically read from a file (like `less` or `grep`) will also read from piped-in input. 

For example, this command will list the files and directories in your home directory:

{% highlight sh %}
$ ls ~
{% endhighlight %}

You can count the number of items in your home directory by passing this output to `wc` (**w**ord**c**ount) with the `-l` flag, which tells it to count lines:

{% highlight sh %}
$ ls ~ | wc -l
{% endhighlight %}

One of the most common uses of `|` is to make long command output more readable using `less`. This example uses `find` to list all the files in your home directory, then pipes the output to `less` so you can scroll through it:

{% highlight sh %}
$ find ~ | less
{% endhighlight %}

Remember, you can press <kbd>q</kbd> to quit `less`.

### More complicated examples

#### How many lines of code did you write for this class?

First, use `find` to locate all the Java files in your `Sites/cs201` directory:

{% highlight sh %}
$ find ~/Sites/cs201 -name "*.java"
{% endhighlight %}

Use `cat` to print out these files, and pipe to `wc` to count lines:

{% highlight sh %}
$ cat `find ~/Sites/cs201 -name "*.java"` | wc -l
{% endhighlight %}



#### How many times have you used `ActionListener` since starting Tetris?

Use `find` to locate files newer than the `Tetris` directory:

{% highlight sh %}
$ find ~/Sites/cs201 -name "*.java" -newer ~/Sites/cs201/Tetris
{% endhighlight %}

Use backticks to pass these files to `grep` and search for "ActionListener":

{% highlight sh %}
$ grep ActionListener `find ~/Sites/cs201 -name "*.java" -newer ~/Sites/cs201/Tetris`
{% endhighlight %}

And finally, pipe to `wc -l` to count lines. Here's the whole command:

{% highlight sh %}
$ grep ActionListener `find ~/Sites/cs201 -name "*.java" -newer ~/Sites/cs201/Tetris` | wc -l
{% endhighlight %}

