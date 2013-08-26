---
title: "Lua: Test Program Interface"
layout: default
---

# Lua: Test Program Interface

[The Lua programming language](http://www.lua.org/about.html) is an interesting. It's extremely minimal, fast and
designed to be embedded in C programs.

I'm always looking for something to use for hp93k TestMethods and Test-Program
Interface tools that's quick and light-weight for development. C is too
low-level, requiring you to worry about memory-management and C++ is a
monstrosity while still being low-level. To make C++ workable you need to add
some heavy libraries like [Boost](http://www.boost.org/) and even then,
experience shows it doesn't yield the breezy, on-the-fly coding experience I
want when working on the hp93k.

## Why not Python?

While I'm a big fan of the [Python programming
language](http://python.org/about/) there's times when it feels a bit heavy.
With Python you can quickly develop all sorts of programs, even using C
libraries, and I've used it to make User Procedures, Test Methods and even Test
Flows with some success. But, actually embedding Python in a test program comes
with some drawbacks.

The main drawback to Python is that its tricky to install a new Python
interpreter on old-ass Redhat. It's a fast evolving langauge and a lot of the
libraries and langauge constructs that are exciting are also new. Just looking
at version numbers, Redhat Enterprise Linux 3 Update 7, which is recommended
for running SmarTest through version 6.5.4. Comes with Python 2.2. RHEL 5u6,
which uses a 64-bit kernel and is recommended for Smartest 6.5.4 and newer
comes with Python 2.4. The stable Python 2.x branch is at 2.7 and the newer
Python 3.3 is what's recommended for new projects.

Adding to the dependency hell is that even though SmarTest 6.5.4 to 7.2 run on
a 64-bit kernel, all of the libraries and executables used for test programs
are still 32-bit and there's a whole 32-bit infrustructure that ships with the
default install, but the only Python (and libpython that you need for
embedding) that ships with it is 64-bit. So in order to use it in test programs
you have to build a 32-bit version and ship it with your test program.

Building 32-bit Python under RHEL5u6 is a fraught process. I plan to write up
how to do it in a future post, but for now, suffice to say, if you want to
embed Python in new test programs, you're gonna have a bad time.

In addition to the hassle, distributing Python 3.3.2 with your test program
adds a monster 16 MB compressed. This is because Python believes in shipping
with "batteries included". The downside being megabytes of libraries you will
never use. There's tools to trim this down for distribution but this is just
adding to the hassle.

The source for Lua comes in around 250 kB compressed. But you will also want to
add some libraries [which you can browse on LuaRocks](http://luarocks.org/repositories/rocks/).

## Building Lua

Building Lua and embedding it in a C program is straightforward on both of the
Redhat platforms. It's tiny and easily distributed with your test program.
Let's build it under RHEL5u6 and RHEL3u7 the instructions are the same:

    wget http://www.lua.org/ftp/lua-5.2.2.tar.gz
    tar xfz lua-5.2.2.tar.gz
    cd lua-5.2.2
    make linux MYLDFLAGS=-m32 -L/usr/lib -lncurses MYCFLAGS=-m32

Easy. Except for that business with `MYLDFLAGS` and `MYCFLAGS` looks a little hairy. Get used
to it! This is your future building 32-bit programs for 64-bit Redhat.

For a quick test, fire up the lua interpreter:

    src/lua
    Lua 5.2.2  Copyright (C) 1994-2013 Lua.org, PUC-Rio
    > print("hello lua")
    hello lua
    <CTRL-D>

`<CTRL-D>` or `<CTRL-C>` ends the session.

You don't need the Lua interpreter for embedding, but it's good to play around
with for learning the language, debugging and writing scripts. If you want to
install it then you should have a directory setup with your path pointing to,
to install software in. If you don't have that then make one like this:

    mkdir $HOME/opt

Then add it to your path in `$HOME/.bash_profile` which is basically adding the lines:

    PATH=$HOME/opt/bin:$PATH
    LD_LIBRARY_PATH=$HOME/opt/lib

Then logout/login to apply it to all of your sessions or just type

    . ~/.bash_profile

in a terminal to apply it for this session. Then rebuild and install lua with:

    make clean
    make linux MYLDFLAGS=-m32 -L/usr/lib -lncurses MYCFLAGS=-m32 INSTALL_TOP=$HOME/opt install

##  
    
    
