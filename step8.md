---
layout: default
title: Easter eggs
prev: step7.html
next: step9.html
progress: 89%
---

There is a long history of impressive text-only tricks. Quite a few of these are built into many modern computers! Here are some to try:

#### Let it snow
This is actually a (short) program written in a programming language called Ruby. Try pasting it into your terminal.

{% highlight sh %}
$ ruby -e 'C=`stty size`.scan(/\d+/)[1].to_i;S=["2743".to_i(16)].pack("U*");a={};puts "\033[2J";loop{a[rand(C)]=0;a.each{|x,o|;a[x]+=1;print "\033[#{o};#{x}H \033[#{a[x]};#{x}H#{S} \033[0;0H"};$stdout.flush;sleep 0.1}'
{% endhighlight %}

#### Go on an adventure
The `emacs` editor is full of hidden gems. One of the oldest is this game from 1983:

{% highlight sh %}
$ emacs -batch -l dunnet
{% endhighlight %}

It's worth mentioning that this game was written by an [accomplished computer scientist and Segway polo player](http://www.driver-aces.com/ronnie.html).

#### Watch a movie
The `telnet` command is a little like `ssh`, except it isn't secure. It's not used for logging in anymore, but it's still useful for some fun applications:

{% highlight sh %}
$ telnet towel.blinkenlights.nl
{% endhighlight %}

When you're done, press <kbd>control</kbd> + <kbd>]</kbd>, type in "quit", then press <kbd>return</kbd>.

[This website](http://www.ascii-wm.net) broadcast a live stream of the 2006 world cup via `telnet`, although the video is no longer available. You can see some screenshots of the "footage."

#### Visit the "doctor"
Start up `emacs`. Press <kbd>esc</kbd> then <kbd>x</kbd>. Type in `doctor` and hit <kbd>return</kbd>.

#### Play tetris
Start up `emacs`. Press <kbd>esc</kbd> then <kbd>x</kbd>. Type in `tetris` and hit <kbd>return</kbd>.
