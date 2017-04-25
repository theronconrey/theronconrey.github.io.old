---
layout: post
title:  "ZFS on CentOS and dealing with the rough edges"
date:   2017-04-25 18:00:04 -0500
categories: infrastructure
tags: infrastructure
comments: false
image:
  feature: abstract-1.jpg
  credit: theronconrey

---

While I've been busy working on infrastructure at a crazy scale during my day job, I've still looked for interesting projects and storage solutions to tinker on.  ZFS has been a staple and recently I needed to move a ZFS pool from an aging server somewhere new. I decided, mostly because of my work with CentOS in the day job, to stand up a new CentOS server to present the pool from there. While installing ZFS is pretty straightforward these days, there are a couple things after you're done that need to be done in order to make sure it consistently loads up on reboot, and is available as storage. To that end, let's go ahead and get started from the begining with installing CentOS and ZFS.


# Installing CentOS

After a minimal CentOS installation, you'll want to ensure that the EPEL repository is installed.

{% highlight rub  %}
$ sudo yum -y install epel-release
{% endhighlight %}

#Installing ZFS on Linux
The documentation at the ZoL site are pretty solid.
If it's not we'll need to load a KVM specific module with the nested option loaded.  The easist way to change this is using the modprobe configuration files:


# References:
* [ZFS on Linux CentOS documentation][centos-zol-guide]


[centos-zol-guide]: https://github.com/zfsonlinux/zfs/wiki/RHEL-%26-CentOS
