---
layout: default
title: Coming Attractions
---

# Coming Attractions

So, I've got this [new weblog](/index.html) and I aim to fill it with
interesting stuff about hp93k. Here's some ideas for future posts.

It will take a while to grind through all of these ideas. Let me know if
there's something you'd like to read about soon, or suggest new ideas in the
comments.

If you'd like to write a post, submissions are welcome!

## Category: hp93k Test Engineering

Specific advice on how to build test programs; Understanding important
technologies.

### Write a Vector Converter in 20 Lines of Python!

### Turn Your SmarTest Workstation into a VM so You Can Take it Anywhere

Basically, how to convert a Linux hard-drive into a VirtualBox image.

### Dumpster Diving

My favorite Go/Semi articles and bits of documentation.

### Vector Conversion: The Key is Understanding Timing

Reading the standards, or your own products data sheet, helps you figure out
how to convert VCD to test vectors. Also, it doesn't hurt to understand how the
hp93k implements vectors and timing.

### Multiport -- Why I Go To The Trouble

* Memory Savings
* Compression
* Vector Editing
* Protocol Dumping

### v2b, ait, aiv -- Can Run on Any Linux

Did you know you can run the hp93k ASCII tools under any Linux, such as the one
you're running on your laptop? (You're running Linux on your laptop, right? At
least an Ubuntu VirtualBox) Here's how to install them.

### What's in my Backpack

A photo essay.

* Hex wrenches
* ISE badge
* Oscilloscope probes
* [Oscilloscope probe positioners](http://www.home.agilent.com/en/pd-1643894-pn-N2786A/two-leg-probe-positioner?nid=-34382.898958&cc=US&lc=eng)
* Digital volt meter
* Mini oscilloscope
* Macbook
* Notepad and pens
* Chip sucker
* Trays and trays of DUTs

### Testing your Tests

Why (and how) test program development should be **Test-Driven**.

A test program is like any other program: slow, buggy and late. In all
seriousness a test program is a program and we should apply the same successful
models that web developers and application developers apply to deliver
reasonable quality.

The hp93k framework gets in the way, but with some effort you can implement
[Test-Driven Development](http://en.wikipedia.org/wiki/Test-driven_development)
which can greatly reduce the number of mistakes you ship.

### Some Handy Firmware Commands Everyone Should Know

Off the top of my head:

* FTST? -- Run a functional test
* SREC -- Temporarily mask some outputs
* DFPN? (@) -- Get list of defined pins
* RLYC -- Control the tester's relays
* SVLR -- Temporarily change a timing or level spec

### Don't Blow Up Your IOs -- Start Every Test Program With Level Set 0!

Apparently, every time you Connect or Disconnect there's a 5.5 V pulse for a
few milliseconds. Older IOs on obsolete process technologies were robust and
didn't care. Fancy new IOs (even bog-standard 3.3V CMOS) tend curl up and die
after a certain amount of abuse. 

This is a known issue and you can program the mysterious **Level Set 0** to
adjust clamps and termination during connect and disconnect. It's a bit of a
pain, but that's why we have jobs.

Only Pinscale and newer testers support Level Set 0. Perhaps someone would
prefer that you retire your old C400?

## Category: hp93k Community

### Building a Community of hp93k Test Engineers

Some ideas for building an hp93k community. Popular and open technologies
benefit from constant, open communication between practitioners. If I were a
JavaScript developer I would have access to all these things:

* [Newsgroup](https://groups.google.com/forum/#!forum/comp.lang.javascript)
* [Mailing list](https://groups.google.com/forum/#!forum/js-tools)
* [IRC](http://irc.lc/freenode/#javascript/t4nk@@@)
* [Open-source projects](https://github.com/trending?l=javascript)
* [Meetup](http://www.meetup.com/jsmeetup/)
* [Independent conferences](http://lanyrd.com/topics/javascript/)
* [Blogs](http://dailyjs.com/), [blogs](http://ejohn.org/category/blog/) and [more blogs](http://stackoverflow.com/questions/409056/top-rated-javascript-blogs)

Their community has exploded in the past 10 years while my community has a
[poorly-attended, corporate-sponsered anual event](http://www1.verigy.com/voice/index.htm)
and that's basically it. I need to get to work on this.

### Where's the hp93k Test Engineering Community?

* [Go/Semi](http://www1.verigy.com/ate/news/newsletter/index.htm)
* [Voice](http://www1.verigy.com/voice/index.htm)
* [Advantest press releases](http://www.advantest.co.jp/news/en-index.shtml)

... and I'm depressed

## Category: hp93k Scripts

### convert.py -- A Flexible, Open-Source Vector Converter

### jtagvec.py -- Tracking JTAG Transactions in your Test Vectors

### release.py -- A Script for Releasing Your Test Program

* Build all your various codes in a new environment
* Set flags for production
* Update revision number
* Git tagging

### 93kon 93koff

Scripts for starting SmarTest from the command line.

### dot_empty.py

Place .empty files in empty subdirectories so `git add .` will record them.
(Why do you need empty subdirectories anyway SmarTest?)

## fixeqsp.py

[Fix broken timing and levels files by updating EQSP byte counts.](/2013/08/21/quick-script:-fix-eqsp.html)

## Category: hp93k Logging and Data Analysis

### A Database for Your Logs

### Understanding STDF

### Understanding Event Datalogging

### evlog2json -- Better Logging with JSON

### Analyzing Data with Python and PANDAS

Python offers some awesome tools for data visualization and analysis. The
trouble is getting your data in.

## Category: hp93k Software Tool Reviews

### Tool Review: Tessent

### Tool Review: Open-Source STDF

There's a surprising number of open-source STDF readers.

* [libstdf](http://freestdf.sourceforge.net/)
* [RADAR](https://sites.google.com/site/stdfradar/)
* [stdfparser](http://code.google.com/p/stdfparser/)
* [pystdf](https://github.com/cmars/pystdf)

Things must be nice in the Teradyne world.

### Inovys

[Inovys](http://www1.verigy.com/cntrprod/groups/public/documents/file/wcmd_001404.pdf)
is a product that helps diagnose scan failures. Apparently you hook a laptop up
to the tester and it drives many variations of patterns and conditions and
gives you something you can use to improve your ATPG fallout and performance. I
must try it.

### Tool Review: Galaxy Data Analysis

[Galaxy](http://galaxysemi.com/) is a tool used by Test and Product Engineers
to analyze log data coming off the production line. I honestly haven't tried
it. But I do have access to copy. So maybe I should.

### Tool Review: Vtran

I've been hearing about [Vtran](http://www.sourceiii.com/product-vtran.php) for
years but since I write my own vector conversion scripts (and once worked for a
long time, developing a commercial competitor,
[V2soc](http://www.nanoisi.com/product_subpage1.php)) I haven't tried it. But I
hear good things so maybe I'll give it a spin.

### Tool Review: V2soc

I used to write this vector converter,
[V2soc](http://www.nanoisi.com/product_subpage1.php) but since leaving that
company I haven't used it in many years. It would be interesting to see how far
it's come.

### Tool Review: Test Insight VCD2ATE

Yet another VCD converter I haven't tried,
[VCD2ATE](http://www.testinsight.com/products/design-to-tester-conversion/vcd2ate.aspx).
Test Insight's salesmen seem friendly. Maybe they'll give me demo license for
review.

## Category: hp93k HOWTOs

### Run SmarTest on your Laptop!

It's easy to setup SmarTest in VirtualBox. Why have a dedicated workstation or
VM hosted inside your corporate network. Test Engineers go places like labs and
you never know when you'll want to hack.

### Setup a Remote Shared Session with VNC

Sometimes you need to debug a program running on a far-away tester. VNC is
already installed on your workstation. You can use it to setup a desktop shared
by the guy on the testfloor and you at your remote mountain lair.

### GVIM 

If you're new to Vim, perhaps this nice GUI will help you stay productive while
you learn.

### ~/.vimrc -- The Least you Should Know

You're using Vim for everything right? A few simple customizations make
everything better.

### ~/.profile -- The Least you Should Know

It breaks my heart to see engineers struggling with a broken terminal. Old
`.profile` files carried over from the bad old days of HPUX should be deleted.
Here's a template to help you start over.

### Version Control 1 -- Sooner or Later You'll Realize it's Essential

### Version Control 2 -- GIT

Forget CVS and Subversion. The new generation of version-control tools are much
better.

How to build git on your SmarTest workstation, on your testfloor workstation,
and how to setup a server to pass patches between them.

### Clock Skewing -- How and Why

Sometimes you have to fiddle with the clock/data timing relationship, even doing
searches on-the-fly for a "passing window". The reason is poor DFT. Complain to
your local designer. But, for now, here's how to do it.

## Category: hp93k Research Reviews

There's a few relevant papers to be had. I just came across [this one on scan
debug](http://www1.verigy.com/cntrprod/groups/public/documents/file/wcmd_001404.pdf)
from the guy who made Inovys.

## Category: hp93k Checklists

Checklists are a good idea. I read [The Checklist
Manifest](http://www.amazon.com/The-Checklist-Manifesto-Things-Right/dp/0312430000)
and was convinced for a while that checklists would save the world. I wrote
a few. Sometimes I even use them.

### Program Release Checklist


## Category: Running a Testfloor

### Citrix Sucks -- A Better Way for Remote Logins

Exporting old-ass Linux desktops is not one of Citrix's strong points. An open
letter to the ASE group.

## Category: The Test Business is Hard

### Let's Go Consulting

### It's Hard to Sell Testers

### It's Hard to Run an Off Shore Production Facility

### It's Hard to Run an Independent Lab

### It's Hard to be a Test Engineer

### It's Hard to be a Test Engineering Consultant

### It's Hard to Hire a Test Engineer

### It's Hard to Hire a Test Engineering Consultant

### Is it Time for an Indie Tester Company?

With Advantest's recent purchase of Verigy, we're down to three major tester
companies: Teradyne, Credence/LTX and of course Advantest.

I've been thinking a lot about tester design and with lessons learned I think
we could build a much better tester, casting off the shackles of history. But
who will do it? Agilent would certainly be in a good position to get back in
the business. Any major test equipment vendor such as Lecroy or Tektronix has
a leg up too. Maybe someone should put together a plan and head on up to Sand
Hill Road. Maybe I should.


## Category: Vector Conversion


## Category: hp93k System -- How it Works

### Dumpster diving in /opt/hp9300/soc

You can learn a lot about how SmarTest works by combing it's file tree.

### Layers: Firmware Commands

"Firmware Commands" don't really let you talk to the firmware, but they do
provide an API to control SmarTest -- and by extension, the hp93k hardware --
which, unlike the TestMethod API, is completely thorough.

You can learn a lot about what SmarTest is thinking by monitoring them. Run
`hpt` and enter `diag 2` then `tail -f /var/opt/hp93000/soc/MCDLog` or wherever
the UI report tells you to the commands and responses are being dumped.

They're really handy to know about because sometimes there's no other way.

### Layers: TPI -- Test Program Interfacing in C

The Test Program Interface is the old C API for interacting with SmarTest. It
allows you to control various aspects of SmarTest. Unfortunately it hasn't been
updated to reflect new features in many years, so you can no longer control
everything. But it's still plenty useful.

* User Procedures -- They're like TestMethods but lower level and they break more across SmarTest versions.
* Execution Input -- Write C extensions to the Application Model. Why aren't Application Models C in the first place?
* Data Bridge -- A pointless redundancy that you may still need anyway to fix up your logging.

### Layers: The Application Model

At some point we needed a way to control the coordination of test programs and
handlers outside of the test program itself. So, some bright engineer said to
himself, "I know. I'll invent my own language that does this and only this. I
mean, there's many serviceable languages out there, but I took a compiler class
at community college and how else am I ever going to use that knowledge?"
Welcome to Hell.

### Layers: Workorders

There's this whole complex infrastructure for workorders and I'm pretty sure no
one uses it. Still, it's kind of interesting to see how some old HP engineers
thought you would run your testfloor.

### Layers: TestFlow

### Layers: TestMethods

### Layers: Logging

### Build Your Own Tester

The hp93k is basically:

* A barrel of memory 
* Timing and levels formatters
* A clock
* Simple Voltage and current-measuring instruments
* Slightly complex Analog, SERDES and RF instruments
* All connected to a computer
* Software

With a little elbow grease you could make your own. That could lead to a fun
series of articles. But I probably want to get a group together and maybe some
funding before I do that.


## Category: hp93k Open-Source Advocacy

Y u no post TestMethods on [Github](http://github.com)?

### Hack!

Test Engineers of world unite! This post is blatant advocacy for open-source
cooperation between everyone working on the hp93k for the good of all.

### Are You Running Linux on your Laptop? You Should!

Advocacy: Your job takes place in a Linux environment. It benefits you greatly
to use Ubuntu as your daily driver. There's very few hangups after install and
every hangup that does occur just increases your valuable Linux knowledge.

Besides, it's great to have all of your favorite tools all the time.

An alternative is to run Linux in a VM under windows so you can keep your Excel
and Outlook. But come on. Excel is Lame and OpenOffice is all but a drop-in
replacement. Your company really should run Outlook Web Mail, or ideally, Gmail
and leave you to your operating system preferences. You can always run an XP VM
under VirtualBox for occasional Windows needs.

Links to resources on

* Installing Ubuntu
* Setting up VPN access
* VirtualBox
* Ubuntu Guides
* and stuff I like to tweak my experience with like dwm.

### Open-Source (Almost) Everything

Rather than try to cook up a great argument for why you should open source your
vector convert and your test methods, I'll start by open sourcing mine. Then
I'll point you to the excellent article by Tom Preston-Werner:
[Open Source (Almost) Everything](http://tom.preston-werner.com/2011/11/22/open-source-everything.html).


### Why is There so Little hp93k Open-Source

Other developer communities have succeded tremendously in sharing. Just think
where the web was 10 years ago. And look at it now? This fancy blog is all open
source.
([Source code is here](https://github.com/gitfoxi/gitfoxi.github.io).)

hp93k isn't a huge community, but there's at least thousands of us around the
world, writing test programs and related stuff. Just think, if we joined
forces, our programs, platforms and scripts would improve by a multiple of
thousands.

So what's stopping us? Do we really want to go around repeating the same
mistakes, living with the same bugs and the same lousy platform forever? Is
there a weird culture of closedness in the semiconductor industry? Am I just
being paranoid? Let me know in the comments.


### How to Open Source

A quick tutorial to get you started with git and github.


## Category: hp93k Open-Source Software You Need (And How to Build on Old-Ass Redhat)

* git
* gtkwave
* python
* lua
* pylab (python + pandas + ipython + scipy + numpy)
* mysql

## Category: Design For Test

Testing is hard. Sometimes impossible. It can be greatly improved through
application (and not miss-application) of modern methods. Learn how to work
with designers to make sure DFT is correct before tapeout.

Often, a bit of DFT can replace a lot of expensive time and test equipment.
Modern PCIe IP is a good example of an interface with a built-in tester.

### DFT: Shopping for IP

### DFT: Shopping for DFT Tools

### DFT: Integrating Diverse Technologies with a Test Access Port

* JTAG, PJTAG, IJTAG or roll your own?
* Parallel or serial?
* Multiplexed or dedicated?

### DFT: Synchronicity

* Who drives the IO clock? (The tester, always the tester)
* FIFOs and synchronizers and Verilog -- welcome to Hell

### DFT: All About ATPG

### DFT: Cell-aware ATPG

### DFT: All About Boundary Scan

### DFT: All About Built In Self Test (MemBIST, LogicBIST)

### DFT: Loopback!

### DFT: Efuse is the Devil

## Category: hp93k Skills

### It's Hard to Parse STIL (But You Can Do It!)

### It's Hard to Parse WGL (But You Can Try!)

In which I post an unofficial spec for WGL. And ask if anyone can find a copy
of the official one?

### Understanding STIL

### Understanding WGL

### JSON, YAML, XML, Python, Lua and C -- Languages You Should Know

### All about IJTAG

### All about JTAG

### All about IP Cores

### Testing DDR 1-2-3

### Testing PCIe (And other SERDES)

### Testing DAC

### Testing PMU

### Testing ADC

### Testing RF

### Testing High-Speed Interfaces

### Testing Vanilla CMOS IOs

### Digital Capture (Has Gotten Crazy)

### Digital Source or Modify Vectors on the Fly?

### Understanding Digitizer and Waveform Generator Specs

## Category: hp93k Loadboard Design

### DAC Testing: Amplifiers on my Loadboard

Say you're working on a DAC or other analog signal source which puts a tiny
signal. Say it has a weird output impedance like 10kohms that doesn't match
your transmissions lines very well. And say you have to measure a high-speed,
high-SNR signal. How to select a quality amplifier to fix your impedance
mismatch and signal-level problems without adding (much) distortion.

### Get Involved in Loadboard Design

Here I'll encourage you to learn to draw some schematics and present. There are
opportunities to exploit and pitfalls to avoid by taking an active role in your
board design.

### Loadboard Design Checklist

### It's Hard to Select a Loadboard Contractor

The upshot is that you have to learn quite a bit about board design and really
care about board design to get it right the first time.

### Why are Loadboards so Expensive?

* Expensive substrates
* Large area
* Many layers
* Low volume
* Design intensive
* Fancy components (Looking at you, Teledyne)

### Add a 1k Resistor Across All Power Supplies

In fact, you want a resistor across all capacitors which may be left floating
without a natural discharge path.

## Series: Meet a Test Engineer

In which we interview interesting people about life, career, travel, testfloors
and of course hp93k fandom.

## Category: Project Management

### Organizing Your Production Process

This is a difficult topic. Production processes run on forms and emails and
checklists. You have to design a process that is rigid to ensure quality and
traceability but flexible enough to accommodate future products.

### Organize Your Program Development

I could write a novel. Elements include:

* Version Control
* Product Development Phases
* Qualification
* Characterization
* Final Test and Final QA
* Documentation
* Scheduling

### Estimating Project Schedules -- It's Worth a Try

Never perfect, and rarely successful, project management is something you have
to do anyway. 

Learn about [Planning Fallacy](http://en.wikipedia.org/wiki/Planning_fallacy).
Science has proved that you will always underestimate the time it takes to
complete a task. 

Learn about [Irreducable Errors](http://www.thefullwiki.org/The_Mythical_Man-Month#wikipedia_The_Tendency_to_Irreducible_Number_of_Errors). You'll always have bugs no matter how many you fix.

Make a credible effort anyway.

## Category: Improving SmarTest

### A Database for Encryption Keys

### Stop Inventing Domain Specific Languages (You Jerk)

### Teamwork -- SmarTest MFH or Roll Your Own

### Reverse Engineering The Event Datalog

How evlog2json connects to the Event Datalog Stream without using the libdrl.

### Reverse Engineering VECC Compression

One thing that keeps me using v2b rather than baking its functions into my
vector converter is the undocumentedness of VECC compression. At some point I
was looking at it carefully. It seems to be a combination of 
[LZW](http://en.wikipedia.org/wiki/Lempel–Ziv–Welch) and 
[Huffman Coding](http://en.wikipedia.org/wiki/Huffman_coding)
with variable word width.
Is it time I finished that project?

### Reverse Engineering The MCD

Interfacing the MCD is as easy as:

    HPInit();
    HpFwTask(...);
    HPTerm();

But it leaves a few things to be desired. Notably I can't clone it and make a
better one. ... Or can I?

### Reverse Engineering SmarTest with Hpt

Analyzing MCDLog to learn more about hp93k.

### Why Every GUI Sucks Harder than the One Before -- And How To Fix It

GUIs are basically unhelpful in software development and test-program
development is no exception. Think about it: Visual Studio, Xcode -- they only
provide GUIs for developing other GUIs!

The thing to do is to focus on developing interfaces that are:

* Text based
* Easily parsed -- For scripting.
* Solidly testable -- GUIs are impossible to automate testing. Automating testing is something I would hope the SmarTest developers know something about.
* Industry standard -- so you can hire people who already speak the language

Basically every one of the 20-odd mini-languages in SmarTest could be replaced
with JSON, YAML, C and Lua -- and the world would be a much better place.

Once you've got the text-based interface down then you can think about special
cases where conveying information graphically is helpful. But be careful: User
Interface design is both a science and an art. You probably don't have the
research or the resources to do a good job with too many of them.

Seriously, if it made sense to click a menu and select an 'If' block and fill
out a dialog and place it in the flow of your program and move functions into
it's 'then' and 'else' branches then that is how software would be developed.
Instead, this is how software is developed:

{% highlight python %}
if thing:
    print "Thing!"
else:
    print "Nothing"
{% endhighlight %}

I just typed that quicker than I could have opened a testflow in eclipse, let
alone found the palette and filled out the dialogs and look it's completely
clear! `</rant>`

### Hacking FLEXlm

Say you've just purchased a SmarTest license and you're waiting for them to
mail it to you (seriously, haven't you heard of email?). You're schedule won't
let you sit on your hands however long it takes a box with a certificate to
arrive from Singapore. Is there any way to start working now? There is.

## Category: Bug Reports

In which I submit unsolicited but reports to the Advantest SmarTest team

### Continuity logs only one pin name

In 6.5.4 the binary datalog lists the first pin name in a continuity test for
all of the pin names.

### MAPI defines a lot of common units

If you try to name a variable like

    int V;
    V = 7;

you're gonna have a bad time. This is thanks to a bunch of units defined in
`MapiUnit.h" looking like:

    #define    nV        *1.000000e-09
    #define    uV        *1.000000e-06
    #define    mV        *1.000000e-03
    #define    V
    #define    KV        *1.000000e+03
    #define    MV        *1.000000e+06
    #define    GV        *1.000000e+09

I can't tell you how many times I've wanted to name a variable `Kohm`, `dBm`,
`msec` or `Vpp` (they even stole `CODE`) and been confronted with some crazy,
impossible to debug compiler errors.

Being able to add units to your code flexibly is a cool, almost-magical
feature. But in this case the price is too high. Guys, you've broken the
cardinal rule against poluting, the global namespace.

This would be quite convenient if it wasn't biting me in the ass every time I
try to use a 1-4 letter variable name. Perhaps an indictment of C++. But C++
does have namespaces so this is just gratuitous. Would it be so terrible to
type `100 TM::uV` instead of `100 uV`?

## Using NIXos to create a stable platform with a future

Also, an amazing new way to distribute test programs to offshore.

## Python, Lua, LuaJIT, Golang, SWIG -- Installing and Wrapping

