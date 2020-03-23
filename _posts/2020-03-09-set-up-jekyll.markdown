---
layout: post
title:  "Setting up Jekyll"
date:   2020-03-09 14:01:43 +0800
categories: Ruby Jekyll linux
---

In this post we are going to build a development environment to start building websites with **Jekyll**.

![alt text](https://jekyllrb.com/img/logo-2x.png "Jekyll")

Jekyll is a blog-aware, static site generator writen in **Ruby** perfect for personal, project, or organization sites.

> Think of it like a file-based CMS, without all the complexity. Jekyll takes your content, renders Markdown and Liquid templates, and spits out a complete, static website ready to be served by Apache, Nginx or another web server. Jekyll is the engine behind GitHub Pages, which you can use to host sites right from your GitHub repositories.

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh].

[jekyll-docs]: http://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll

## Requirements

As it was mentioned before, *Jekyll* runs in *Ruby*, therefore we need to install Ruby version 2.4.0 or above, including all development headers.

You chan check if you already have ruby installed by running `ruby -v`

### Installing Ruby in Ubuntu 18.04 using snapd

Snappy is a software deployment and package management system developed by Canonical for the Linux operating system.

If you are not sure if you already have snap, check it running `snap --version`. If you see something like this:

{% highlight bash %}
$ snap --version

snap    2.43.3
snapd   2.43.3
series  16
kernel  4.15.0-66-generic
{% endhighlight %}

If you see nothig then you have to install snap. Run:

{% highlight bash %}
$ sudo apt update
$ sudo apt install snapd
{% endhighlight %}

After installing, we have to make sure that snap bin in included on the system Path. To do so, run:

{% highlight bash%}
$ which snap

/usr/bin/snap
{% endhighlight %}

If you dont see the `/usr/bin/snap` outcome, then you have to manually include snap on the PATH environmental variable. To do so, you have to edit `/etc/environment` and add `:/snap/bin` to the end of the PATH string.

Great! Now you can proceed to install *Ruby*:

{% highlight bash%}
$ sudo snap install ruby --classic
{% endhighlight %}


If everything installed correctly, you should now have Ruby and RubyGems installed properly:

{% highlight bash%}
$ ruby -v
ruby 2.7.0p0 (2019-12-25 revision 647ee6f091) [x86_64-linux]

$ which ruby
/snap/bin/ruby
{% endhighlight %}


{% highlight bash%}
$ gem -v
3.1.2
{% endhighlight %}

### Install GCC and Make

{% highlight bash %}
$ sudo apt install gcc, g++, build-essential
{% endhighlight %}

So far, we have installed Ruby and and it's package manager (or 'gem' manager), RubyGems. The next step would be install Jekyll and Bundler.

Bundler provides a consistent environment for Ruby projects by tracking and installing the exact gems and versions that are needed.

### Install Jekyll

{% highlight bash%}
$ gem install jekyll
{% endhighlight %}

### Install Bundler

{% highlight bash%}
$ gem install bundler
{% endhighlight %}

---

And that is all! Now you can create a new Jekyll site:

{% highlight bash%}
$ jekyll new my_site
$ cd my_site
$ bundle exec jekyll serve
{% endhighlight %}

Browse to http://localhost:4000



<!-- 

Sources

https://jekyllrb.com/docs/

(https://www.ruby-lang.org/en/documentation/installation/)
(https://stackify.com/install-ruby-on-ubuntu-everything-you-need-to-get-going/)


(https://stackoverflow.com/questions/57121916/the-command-could-not-be-located-because-snap-bin-is-not-included-in-the-path)


-->



