---
title: Installation
---

# How to install the test release

## Arch linux

Add the following lines to /etc/pacman.conf.

~~~
[yarrr-testing]
SigLevel = Optional TrustAll
Server = http://repo.yarrrthegame.com/arch/$repo/os/$arch
~~~

Type the following to the terminal.

~~~ bash
# pacman -Sy
# pacman -S yarrr
~~~

## Debian/Ubuntu linux

Add the following lines to /etc/apt/sources.list.

~~~
deb http://repo.yarrrthegame.com/debian trusty multiverse
~~~

Type the following to the terminal.

~~~ bash
# apt-get update
# apt-get install yarrr
~~~

