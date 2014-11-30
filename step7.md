---
layout: default
title: Other commands to try
prev: step6.html
next: step8.html
progress: 78%
---

There are many more commands than we can cover in this lab, but here are a few common ones we haven't covered yet. Try out at least three of these:

#### Learn about new commands
You can read documentation for any command and its options using the `man` (**man**ual) command. For example, `man ls` will describe the `ls` command. Of course, `man` has its own options, so run `man man` to read about them. Use the arrow keys to move around, and press <kbd>q</kbd> to quit.

#### See what's running
The `top` shows a live-updating view of the applications running on a machine. The display includes the amount of memory and CPU being used by each program, along with many other system resources. Press <kbd>q</kbd> to quit.

#### See who's logged in
The `who` command will list all the connected users. There is an entry for each connection, so if you have multiple connections to a machine you will be listed multiple times.

#### Copy files to a remote machine
You can use the `scp` (**s**ecure **c**o**p**y) command to copy files to another machine. The command works much like `cp`, except you can copy to/from a remote machine. For example, you can use a command like this one to copy Assignment 8 from your personal machine to the department file server:

{% highlight sh %}
$ scp -r ~/my/eclipse/workspace/Assignment8 smith22j@royal.cs.mtholyoke.edu:~/Sites/cs201/
{% endhighlight %}

The `-r` flag tells `scp` to copy recursively: it will transfer all the files in a folder. Without this flag, you can only copy one file at a time.

#### Look at the beginning or end of a file
The `head` command will print the first ten lines of a file. Likewise, `tail` prints the last ten. You can specify a different number of lines with the `-c` flag:

{% highlight sh %}
$ head -c 4 HelloWorld.java
public class HelloWorld
{
  public static void main(String[] args)
  {
{% endhighlight %}

If you run `tail -f <filename>`, the `tail` command will "follow" the file. Whenever lines are added to the end of the file, they will be displayed. This is useful for watching output from a program that writes to a file. Press <kbd>control</kbd> + <kbd>c</kbd> to kill the `tail` command when you're finished.
  
#### Compare two files
The `diff` command will show you which lines in two files are different. Just pass in two files that are similar. Lines marked with `<` appear only in the first file, and lines marked with `>` are only in the second file.

#### Other editors
There are many editors available for the terminal, but two of the most popular are `nano` and `vim`.

`nano` is a very basic simple that displays helpful commands at the bottom of the window. Most commands include the `^` character, which actually means to press <kbd>control</kbd>. For example, `^X` is the command to exit. To run this command, push <kbd>control</kbd> + <kbd>x</kbd>.

`vim` is the most popular alternative to `emacs`. There are people who feel very strongly about one editor or the other. The `vim`, short for **vi** i**m**proved, is based on `vi`, short for **vi**sual editor. The main difference between `vi` and `emacs` is that `vi` has modes: you're either in editing mode or command mode. First, open a file with `vim`:

{% highlight sh %}
$ vim HelloWorld.java
{% endhighlight %}

The editor will start in command mode. To move around, use the arrow keys. To begin inserting text at the current position, press <kbd>i</kbd>. Anything you type will be added at the current cursor position. Arrow keys are *supposed* to move around while you're in editing mode too, but sometimes you will need to change some settings for this to work properly. To leave editing mode, press <kbd>esc</kbd>.

To save changes to your file, leave editing mode, type `:w` and press <kbd>return</kbd>. To quit, type `:q` and press <kbd>return</kbd>. If you have modified the file, `vim` will warn you instead of quitting. You can run `:q!` to quit and discard changes. You can combine commands too: run `:wq` to save and quit.

You can open multiple files with `vim`. To open a file, run the command `:tabe <filename>`. You can type part of the filename and press <kbd>tab</kbd> to complete the name. Press <kbd>tab</kbd> multiple times to cycle through all matches.

Open files are displayed at the top of the window. Run the command `:tabp` to move to the previous (left) tab, and `:tabn` to move to the next (right) tab.

Common operations are mapped to keys that are easy to reach from the home-row of the keyboard. In command mode:

- <kbd>h</kbd> moves the cursor left
- <kbd>l</kbd> moves the cursor right
- <kbd>j</kbd> moves the cursor up
- <kbd>k</kbd> moves the cursor down
- <kbd>a</kbd> will begin editing mode *after* the current character
- <kbd>shift</kbd> + <kbd>a</kbd> will begin editing mode at the end of the current line
- <kbd>s</kbd> will delete the current character and begin editing mode
- <kbd>e</kbd> will move to the next whitespace or punctuation character
- <kbd>shift</kbd> + <kbd>e</kbd> will move to the next whitespace character
- pressing <kbd>d</kbd> twice will delete the current line

Run the command `:syntax on` to turn on highlighting when you have a Java file open. There are many other options you can read about online.
