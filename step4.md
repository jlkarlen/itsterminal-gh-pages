---
layout: default
title: Java Packages
prev: step3.html
next: step5.html
progress: 45%
---

Most classes written in Java are placed in *packages*. A package works a lot like a directory for files, but instead of separating them with `/` characters, Java packages are separated by `.`.

When you import `java.util.List`, you are referring to packages. The `List` class is inside the `util` package, which is inside the `java` package.

Packages are useful for grouping related classes together, and distinguishing between different classes that share a name. You may have accidentally imported `java.awt.List`, which does [something very different](http://docs.oracle.com/javase/6/docs/api/java/awt/List.html) from `java.util.List`.

#### Create your own package

To get some practice with packages, you're going to organize a few of the classes you've written for assignments or labs.

First, you'll need to make a `src` directory inside of your `Lab10` directory:

{% highlight sh %}
$ mkdir src
{% endhighlight %}

Next, we'll create a package for this course called `cs201`. To do this, make a directory inside your `src` directory:
  
{% highlight sh %}
$ mkdir src/cs201
{% endhighlight %}

Then, we'll make another package specific to your username. Jane Smith's package will be called `smith22j`. To do this, she will run the command:

{% highlight sh %}
$ mkdir src/cs201/smith22j
{% endhighlight %}

#### Copy in the `ParenthesesChecker` code

Now we'll split your parentheses checker application from lab 8 into packages. Inside of `cs201.<your username>`, we'll add a `util` package to hold data the data structures you wrote, and a `parenchecker` package to hold the application's classes.

Jane can run these commands to create the `util` package and copy in the data structures from Lab 8:
  
{% highlight sh %}
$ mkdir src/cs201/smith22j/util
$ cp ../Lab8/Part1/src/Stack.java src/cs201/smith22j/util/
$ cp ../Lab8/Part1/src/LinkedList.java src/cs201/smith22j/util/
$ cp ../Lab8/Part1/src/LinkedListNode.java src/cs201/smith22j/util/
{% endhighlight %}

Next, she can run these commands to create the `parenchecker` package and copy in her application's class:

{% highlight sh %}
$ mkdir src/cs201/smith22j/parenchecker
$ cp ../Lab8/Part1/src/ParenthesesChecker.java src/cs201/smith22j/parenchecker/
{% endhighlight %}

Organize your source files as shown above, but don't forget to copy in any extra classes you may have created for your application! **Don't copy in your test code**---building JUnit classes from the shell can be tricky.

#### Small code changes

To finish splitting your code into packages, you'll need to make a few small changes to your source code. Every class needs to specify which package it is in. Jane Smith's `Stack` class should have the following line at the top of the file:

{% highlight java %}
package cs201.smith22j.util;
...
{% endhighlight %}

Add the package declaration line to each of your classes. Don't forget that `ParenthesesChecker` is in the `cs201.<your username>.parenchecker` package.
  
Finally, you'll need to tell Java how to find the `Stack` class from your `ParenthesesChecker` source file. The `Stack` class can use the `LinkedList` class without importing it because they are in the same package, but your `ParenthesesChecker` class will need to import `Stack`. This works just like imports from Java's standard library. Jane's `ParenthesesChecker` code should start with:

{% highlight java %}
package cs201.smith22j.parenchecker;

import cs201.smith22j.util.Stack;
...
{% endhighlight %}

#### Compiling and running with packages

Before you can compile, you'll need to make a `bin` directory.

The following command **will no longer work** for compiling:

{% highlight sh %}
$ javac -d bin src/*.java
{% endhighlight %}

That's because the `*` will only match files in the `src` directory. Now your code is split over multiple directories. You can list each source file you want to compile, but that will be tedious. Instead, we can use multiple `*` wildcards:

{% highlight sh %}
$ javac -d bin src/cs201/smith22j/*/*.java
{% endhighlight %}

The first `*` will match both the `util` and `parenchecker` directories, and the second `*` will match all the `.java` files.

Did you get any compilation errors? Make sure you imported any classes you're using from a different package.

The command to run your application is a little different too. You need to give the full name of the class with the `main` method, including its package:

{% highlight sh %}
$ java -cp bin cs201.smith22j.parenchecker.ParenthesesChecker "(()(()))"
true
{% endhighlight %}
