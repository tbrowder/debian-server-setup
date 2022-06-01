# Debian 11 (Bullseye) server setup

### Practical information, scripts, and recipes for setting up a useful, safe, and multipurpose server

When I get a new Debian server spun up from a remote provider, I set it for my use
with customization I've established with almost 30 years of working on Unix and Linux
hosts (Sun OS, Dec, Silicon Graphics Irix, Yggdrasil Linux, Red Hat, Fedora, and Debian).

I went to Debian around 2008 when I got tired of Fedora's constant updates and terrible
packaging system. I love the deb package format and the rolling upgrades which made
supporting my customers much easier.

I retired in early 2014 and have never looked back (although FreeBSD does look tempting,
but I am too old to make that change with the time investment just maintaining
my five plus systems--don't ask!).

I am greatful for the friendly and helpful folks on the Debian users mailing list for
the information on firewalls.

Following are the steps I take for setting up a new host to my liking:

## Before starting

Over the years I have kept my user and sysadmin profiles and customization under version
control: first on the early tools like rcs, then on CVS, Subversion, Mercurial, and Bazaar. I stayed too long
with Bazaar, but finally got all my data under Git version control. My private data I keep
backed up on several hosts, including two in my home. I use Github for all my public
data, plus I plan to keep some private data on Github before too long.

It took me too long to move from Csh to Bash, but all my Bash .bash_aliases, .bashrc, and similar 
dot files are under version control. I also keep individual host setting under version
control.

## The new host

It will get a name and an IP address. I keep all my host names, aliases, and IP
address in each host's /etc/hosts file.

I create a new ssh key set for the new host, and I exchange and set up keys for
the new host to be managed from my main host, my laptop. 

I modify the new host's ssh config files to not allow root login, and I set up sudo 
so I am a sudoer.

I set up legacy iptables and UFW on the new host. There is a Bash script to
accomplish those tasks included here.

I install Debian packages I use via another Bash script (also included). It is not unusual
to have to modify that in the process of upgrading to a new Debian version.

After the system is locked down, and I have all my personlization
working okay, I then install Raku and its cast of supporting modules
for use by the root user as well as regular users. That process
is detailed in my [Raku](./Raku.md) document.

If the new host is to be a web server (the usual
case), I then install the latest Apache httpd server. That process
is described in cookbook fashion, with Bash scripts, in
my public repository at 
[https://github.com/tbrowder/config-scripts/Apache](https://github.com/tbrowder/config-scripts/tree/master/Apache).

