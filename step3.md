---
layout: default
title: Editing
prev: step2.html
next: step4.html
progress: 34%
---

`emacs` is one of the most common text editors used from the terminal. It has built-in support for many programming languages. We'll cover just a few of the basic commands you'll need to use `emacs`.

First, start up emacs to edit a new file called `editing.txt`:

{% highlight sh %}
$ emacs editing.txt
{% endhighlight %}

You'll see a nearly-blank window with a gray bar at the bottom. You can start typing to add text to the file. Use the arrow keys to move around. Add a few lines of text to the file.

You can save your changes by pressing <kbd>control</kbd> + <kbd>x</kbd> *then* <kbd>control</kbd> + <kbd>s</kbd>.

To quit, press <kbd>control</kbd> + <kbd>x</kbd>, then <kbd>control</kbd> + <kbd>c</kbd>.

Display the `editing.txt` file with `cat` to make sure your changes were saved.

#### Opening Files

Start up `emacs` again, but with no arguments this time.

To open a file, press <kbd>control</kbd> + <kbd>x</kbd> then <kbd>control</kbd> + <kbd>f</kbd>. You can type in the name of the file you want to open. `emacs` will finish typing for you if you press <kbd>tab</kbd>, just like the shell. Let's open your `BinaryTreeNode.java` file from assignment 7. There are a few ways to write the path to this file:

The complete path to the file is:

```
/home/smith22j/Sites/cs201/Assignment7/Part1/src/BinaryTreeNode.java
```

This is called an **absolute path** because it starts with `/`, the root of the filesystem. These paths are precise, but often long. You can shorten this by using `~` as a shorthand for your home directory:

```
~/Sites/cs201/Assignment7/Part1/src/BinaryTreeNode.java
```

You can also use a **relative path**. Instead of starting at `/`, you can use your current directory as the starting point. The relative path to this file is:

```
../Assignment7/Part1/src/BinaryTreeNode.java
```

The `..` refers to the directory above your current directory (`Sites/cs201`), and the rest of the path should be familiar.

If you didn't create separate directories for parts 1 and 2, you may have slightly different paths! Tab-completion should help you find your `BinaryTreeNode.java` file.


#### Multiple files

If you press <kbd>control</kbd> + <kbd>x</kbd> then <kbd>control</kbd> + <kbd>f</kbd>, you can open additional files in `emacs`. Open another one of your source files from assignment 7.

To switch between open files, press <kbd>control</kbd> + <kbd>x</kbd> then <kbd>b</kbd>. You can type in the name of the file you're switching to, or just press <kbd>return</kbd> to go to the next file.

To close an open file, press <kbd>control</kbd> + <kbd>x</kbd>, then <kbd>k</kbd>. You will have to confirm that you want to close the file if you have edited it and didn't save your changes.

#### Skipping around a file

You can always move around with arrow keys, but there are special hotkeys for some actions:

- <kbd>control</kbd> + <kbd>a</kbd> moves to the beginning of the current line
- <kbd>control</kbd> + <kbd>e</kbd> moves to the end of the current line
- <kbd>esc</kbd> then <kbd>f</kbd> moves to the next word
- <kbd>esc</kbd> then <kbd>b</kbd> moves to the previous word
