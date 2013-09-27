---
layout: post
title: Making SSH Fast
categories: []
tags:
- Code
- Linux
- OS X
- Tips
status: publish
type: post
published: true
---

In my day to day work, I frequently need to bounce to various SSH servers to see whats happening or put out a fire. Nothing drives me more insane than having to wait 5-10 seconds for SSH. So I put together the various pieces in one nice package for you. (Note: this is for mac/linux only)

First, update your `~/.ssh/config` to be sure that your `Host *` section has at least this in it:

{% gist 1607514 .sshconfig %}

Second, add this shell script to your ~/bin or wherever you keep your shell scripts:

{% gist 1607514 fastssh.sh %}

Edit fastssh.sh and add new lines for the servers you connect to. In my above example, I have 3 servers defined "jira", "gerrit", and "bamboo".

If you want to provide additional SSH arguments like port forwarding, just add them after the hostname/username.

Finally, make sure you install [autossh](http://www.harding.motd.ca/autossh/).

## Cool, what does all of this mean?

* `.ssh/config`
  * `ServerAliveInterval: 30` - Check that the connection is alive every 30 seconds.
  * `ServerAliveCountMax: 2` - If there are 2 consecutive keep alive failures, kill the connection.
  * `ControlPath: ~/.ssh/master-%r@%h:%p` - The location to save persistent connection information.
  * `ControlMaster: auto` - If there is a persistent connection, use it. If not, create one.
* `autossh` - This is a tool, that spawns SSH for you and if SSH quits for an irregular reason, relaunches ssh.

<small><em>Update:</em> Added explanation of some of the configuration and commands below.</small>

[ [Discuss at Hacker News](http://news.ycombinator.com/item?id=3461355) ]
