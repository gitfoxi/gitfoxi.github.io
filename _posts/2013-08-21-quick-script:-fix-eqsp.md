---
layout: default
title: "Quick Script: Fix EQSP"
---

# Quick Script: Fix EQSP

You're debugging your program, fussing with some group definitions. Finally
it's working. You save everything and go home. The next day you go to load your
timing file:

![Timing Bad Content](/images/timing-bad-content.png)

It's happened again. Bad Content. Some edit in some unrelated file or a bug in
a testmethod or smarTest caused the files to be saved inconsistently.

Now, say, for the sake of argument that you know how to fix the timing file.
Maybe you checked your version control (you're using git, right?) and you saw
what changed last and it's obvious. So, you fire up vim, make a quick change in
the wavetable and try to load again.

![EQSP corrupted binary data](/images/timing-eqsp-corrupted.png)

*EQSP - corrupted binary data*

What the hell is "EQSP - corrupted binary data"?

## Binary Data in Firmware Commands

smarTest and programs that you write communicate with the tester through a
text-based interface. These **Firmware Commands** were probably very simple
back when they actually talked to some firmware. (Now they really talk to a
"Message Concentrator and Distributor" which passes them through processes that
actually communicate with the tester.

Firmware Commands are not a bad deal. In fact, they may be the last really
solid design decision that was taken developing smarTest. They're short and
simple and have a strict syntax. For example, to run a quick functional test
you issue the command:

    FTST?

Or to request a list of pins that have been defined, you'd ask:

    DFPN? (@)

However, later models of testers added features that didn't fit the paradigm.
The equation-based timings and levels were implemented by inventing a new
language (instead of adapting Python or Lua to the task. *WHY?*). There was no
convient way to communicate this new timing/levels language to tester software
so what they did was repurpose a facility for transmitting binary data over the
firmware commands text-link to communicate these little sub-files. (Lately,
they've been using it to send XML which I must say, misses a great opportunity
to just re-architect the infrustructure using JSON in a similar way to how web
services do asynchronous communication).

Anyway, the system for transmitting binary data is solid. You start out
transmitting a byte count and then you transmit that number of bytes. This
avoids the confusion that would be caused by semicolons and newlines which in
the text-based interface signify the end of a command.

It looks like this:

    EQSP TIM,WVT,#9000016884

    # JTAG wavetable
    WAVETBL "JTAG ptck"

    DEFINES  ptck

    PINS  JTAG_TCK
      0 "d1:1 d2:F0N"  10_0

    (... the rest of the wavetables ...)

      3 "d1:0 r1:X"  X0_3
      4 "d1:Z r1:X"  X_4
    @

The `@` symbol at the end also signifies the end and it serves as a double
check, just in case someone like you came along and thought he could brazenly
edit his timing file with vim. smarTest didn't find it where it expected to,
and that's the source of the error.

## Fix EQSP

Without futher ado, here's a little Python script that you can use to repair
your broken timing and levels files:

{% highlight python %}
#!/usr/bin/env python

import sys
from shutil import copyfile
import re
from tempfile import mkstemp
import os

if len(sys.argv) !=2:
    print "usage: fixeqsp timing_or_levels_file"

filename = sys.argv[1]
backup_filename = filename + '.fixeqsp.bak'
(fd, extra_backup_filename) = mkstemp()
os.close(fd)
copyfile(filename, backup_filename)
copyfile(filename, extra_backup_filename)

find_eqsp = re.compile('(.*)(EQSP\s+[^,\s]+\s*,\s*[^,\s]+\s*,\s*)#9(\d{9})(.*)',re.DOTALL)

f = open(backup_filename)
w = open(filename, 'w')
in_eqsp = False

for l in f:
    m = find_eqsp.match(l)
    if not in_eqsp:
        if m:
            (pre, eqsp, tnbytes, post) = m.groups()
            in_eqsp = True
            eqsp_l = [post]
            w.write(pre)
        else:  # no match
            w.write(l)
    else:  # in_eqsp
        s = l.split('@')
        if(len(s) == 2):
            in_eqsp = False
            eqsp_l.append(s[0])
            eqsp_l.append('@')
            eqsp_s = ''.join(eqsp_l)
            w.write('%s#9%09d' % (eqsp, len(eqsp_s)))
            w.write(eqsp_s)
            w.write(s[1])
        elif(len(s) == 1):
            eqsp_l.append(l)
        else:
            assert False, 'Expect only one @ per line'

f.close()
w.close()
{% endhighlight %}

[Click here to download fixeqsp](/scripts/fixeqsp).

If you don't know how to use Python, learn how to use Python. It's great. It will help you with so many things. I recommend starting with [Dive Into Python](http://www.diveintopython.net/toc/index.html).

For the impatient, you can use this script by saving into your scripts folder in your `$PATH` with a name like `fixeqsp`. (Please, tell me you have a scripts folder.) Then:

    > chmod a+x ~/scripts/fixeqsp

Then you can use it to fix your timing file with:

    > fixeqsp mytiming.tim

Or you can execute the script directly with

    > python fixeqsp mytiming.tim

## ntk.vim

This little script is convenient. But what I really want is to just to use [Vim](http://www.vim.org) to edit everything. I miss being able to press `F8` to send my wavetables to the tester. (Eclipse, you suck and you know it.) That's why I'm working on **ntk.vim**. It's a Vim plugin that does exactly that. An early version will appear on [my github](https://github.com/gitfoxi) in a few days.

Do you think **ntk.vim** is a good idea? A horrible idea? Do you have suggestions for features? Let me know in the comments. Stay tuned!
