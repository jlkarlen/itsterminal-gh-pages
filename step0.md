---
layout: default
title: Get Connected
prev: index.html
next: step1.html
progress: 1%
---

You'll be completing this week's lab remotely on the server using the `ssh` command. The name `ssh` is short for **s**ecure **sh**ell. This can give you access to another machine through a secure (encrypted) connection. As long as you are connected, everything will work as if you were sitting at the remote machine and using Terminal. What you are about to do can be done on any machine with an internet connection. The same procedure will work to connect to a computer anywhere in the world as long as you have an account.

If you have a laptop with you, we encourage you to try this lab from your laptop. 


#### Open a connection

Jane Smith (username `smith22j`) can connect to that machine with the `ssh` command below. The `$` character is called a "prompt." The terminal prints this out when it is ready to accept a command. **The command won't work if you type the `$` character!**

{% highlight sh %}
$ ssh smith22j@royal.cs.mtholyoke.edu
{% endhighlight %} 

Start an `ssh` connection to the server with the command above. **Don't forget to use your username and the name of the machine next to you**.

If you get an ominous-looking warning the first time you connect to a machine. **Type in `yes` or `y` to continue with the connection**:

{% highlight sh %}
The authenticity of host 'royal.cs.mtholyoke.edu (138.110.92.101)' can't be established.
RSA key fingerprint is 66:35:ae:35:e2:68:62:e7:cd:2c:8a:ae:9a:11:b8:bd.
Are you sure you want to continue connecting (yes/no)? yes
{% endhighlight %}

Next, you'll be asked for your password. **When you're typing in your password, no characters will show up**. Don't worry, it's supposed to work this way!

  <div class="alert alert-dismissable alert-success">
    <button type="button" class="close" data-dismiss="alert">×</button>
    <strong>Why was there a warning?</strong>
    <p>
      `ssh` remembers the *public key* for every machine it connects to. If
      someone else is pretending to be this machine, it will have a different
      public key and `ssh` will refuse to connect instead of possibly sending
      your password to an unknown remote computer.
    </p>
    <p>
      When you connect to a new machine, there is no known key for `ssh` to
      check against. Just make sure you typed the right address and you're on a
      network you trust.
    </p> 
  </div>

#### You're connected

Once you've typed in your password correctly, your terminal will look just like it did when you opened it. Except, this time you're running commands on the server.

Part of what you'll be turning in for this lab is a complete log of all your commands in the terminal. To collect this, run the `script` command:

{% highlight sh %}
$ script
Script started, output file is typescript
{% endhighlight %}

This command will write to a file called `typescript` in your home directory. Every command you run for this lab will be saved to the file. You'll learn how to copy this file into your lab directory as we move through the guide.


