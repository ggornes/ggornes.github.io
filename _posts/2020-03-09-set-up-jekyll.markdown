---
layout: post
title:  "Setting up Jekyll"
date:   2020-03-09 14:01:43 +0800
categories: Ruby Jekyll linux
---

In this post we are going to build a development environment to start building websites with Jekyll.

sudo apt-get install ruby-full

ruby -v



install ruby using snapd

which snapd
snapd --version

sudo snap install ruby --classic

which ruby
ruby -v

(https://www.ruby-lang.org/en/documentation/installation/)
(https://stackify.com/install-ruby-on-ubuntu-everything-you-need-to-get-going/)

voux@ubuntu-droplet-1 ~> ruby -v
Command 'ruby' is available in '/snap/bin/ruby'
The command could not be located because '/snap/bin' is not included in the PATH environment variable.
ruby: command not found


Edit /etc/environment and add /snap/bin in the list then restart your system.
Run the command export PATH=$PATH:/snap/bin
(https://stackoverflow.com/questions/57121916/the-command-could-not-be-located-because-snap-bin-is-not-included-in-the-path)

voux@ubuntu-droplet-1 ~> which ruby
/snap/bin/ruby
voux@ubuntu-droplet-1 ~> ruby -v
ruby 2.7.0p0 (2019-12-25 revision 647ee6f091) [x86_64-linux]
voux@ubuntu-droplet-1 ~>



Jekyll is a Ruby Gem that can be installed on most systems.

RequirementsPermalink
Ruby version 2.4.0 or above, including all development headers (ruby version can be checked by running ruby -v)
RubyGems (which you can check by running gem -v)
GCC and Make (in case your system doesn’t have them installed, which you can check by running gcc -v,g++ -v and make -v in your system’s command line interface)



sudo apt install gcc
sudo apt install g++
sudo apt install build-essential



gem install jekyll bundler


