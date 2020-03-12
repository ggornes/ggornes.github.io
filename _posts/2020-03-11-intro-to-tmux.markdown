---
layout: post
title:  "Introduction to tmux"
date:   2020-03-11 20:01:41 +0800
categories: tmux shell unix
---

![alt text](https://raw.githubusercontent.com/tmux/tmux/master/logo/tmux-logo-medium.png "tmux")


**tmux** is a terminal multiplexer for Unix-like operating systems. It allows multiple terminal sessions to be accessed simultaneously in a single window.

It is useful for running more than one command-line program at the same time. It can also be used to *detach* processes from their controlling terminals, allowing SSH sessions to remain active without being visible. This feature is very useful when running apps or services on the cloud as we can connect to a virtual machine on the cloud, start an app, detach, close the SSH connection and the app will still be running.

![alt text](/assets/img/tmux6.png "tmux example")

## How to install

To install **tmux** just run:

{% highlight bash %}
$ sudo apt update
$ sudo apt install tmux
{% endhighlight %}

## Basic usage

To start a new (unnamed) session just type `tmux`. If you want to give a name to the session, then run `tmux new -s session_name`

