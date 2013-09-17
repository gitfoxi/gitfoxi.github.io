---
layout: default
title: Coming Attractions
---

# Coming Attractions

Congradulations, you dug deep and found that my list of potential blogging
topics is on the internet. Forgive the hasty, outline -- this material is not
ready for prime time.

Let me know what you think.

Let me know if you'd like to contribute to a post.

And if you have any suggestions ... let me know.

So, I've got this [new weblog](/index.html) and I aim to fill it with
interesting stuff about hp93k. Here's some ideas for future posts.

It will take a while to grind through all of these ideas. Let me know if
there's something you'd like to read about soon, or suggest new ideas in the
comments.

If you'd like to write a post, submissions are welcome!

-- TODO: Port this document to vimwiki / Gollum

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
* Protocol Analysis

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

### How Many Test Engineers Working with hp93k?

Estimate the number of test engineers in the bay area and world wide.

Quick estimate: I heard from some Verigy salesman that they had delivered aboug
3000 pinscale machines worldwide. Mutliply that by an optimistic 10 Test
Engineers per tester and you get:

**30,000 hp93k Test Engineers worldwide**

Maybe more if you're willing to include
hp83000, the new SmartScale and the installed base of C400, P600 and P1000.

In the bay area, installed hp93k testers are guestimated at:

* 10 at ISE Labs
* 5 at STS
* 5 at EAG
* 3 at globaltest
* 10 at nVidia
* 2 at Xilinx
* 3 at Broadcomm
* 2 at Advantest HQ

And maybe apply of multiplier of 3 for those unknown to me. Multiplying by 10
Test Engineers per tester, this yields an estimate of:

**1200 hp93k Test Engineers in the Bay Area, 4% of the total community**

That number seems a bit high. I'll have to think about how I'm over estimating
and maybe do an estimate based on job postings and resumes, Voice attendence or
GoSemi subscriptions.

There's a rule called the [90-9-1 principle](http://en.wikipedia.org/wiki/1%_rule_(Internet_culture)
which posits that for Internet content there's

* 1 person actively creating new content
* 9 people that edit, modify and repost the content
* 90 people who passively view it

The upshot is that only 1% of people interested enough in a topic to go look it
up on the internet will contribe to the community knowledge base.

But this fails to account for the dullards who aren't even paying attention. It
sounds like a good question for Quora and while I'm waiting for answers I'll
estimate that 20% are even bothering to occasionally google "hp93k blog"

The bottom line is that you'd expect to see:

* Actively blogging and organizing -- 0.2% -- 60 people worldwide, and just 2-3 in the bay area
* Showing up and contributing something -- 540 people worldwide and 22 in the bay area
* At least occasionally benefiting from low-hanging fruit -- 5400 worldwide and 220 in the bay area

Hey, that's not as bad as I thought. That means that I can potentially reach an
audience of 5400, while recieving comments from 540 individuals. Given the rate
at which I cotton to people I can expect to make upwards of 5 friends worldwide
and as many as 1 here in meatspace.

A successful hp93k test engineer's meetup could attract as many as 25 people:
Enough to fill a large conference room or a small bar.

**In conclusion: I'm encouraged!**


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

My heart goes out to Advantest. After aquiring Verigy they're now in hawk to
the tune of $1 billion and they own the two top semicondutor ATE platforms in
the business.

This gives them a bit of market power. But don't get too jeleous. Advantest
still has to compete with Teradyne and LTX/Credence. Both Teradyne and
LTX/Credence are happy to compete on price. Advantest can hardly afford to play
the price game with their high cost structure necessitated by maintaining two,
basically-equivalent, platforms, all while selling into a marketplace where
they are more likely to canabalize their own sales with any new offering than
they are to take anything away from the competition.

### It's Hard to Run an Off Shore Assembly and Test House

Why put Assemby and Test under the same roof anyway? Is it just to save postage
or is it more about saving face?

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

Ideas:
* Infinite edge placement using time stamps
* timing/levels inheritable, clone-able
* simple text-based interface with GUI for waveform/shmoo only
* 1/10th the cost -- inexpensive enough that you will buy a tester per product
* NixOS
* Move hardware to loadboard -- vertically integrated loadboard and tester manufacturer
* Open source all platform software -- let test engineers fix problems.


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

yRights and restrictions on the use, transfer, and copying of Advantest Software are set forth in Advantest (Singapore) Pte. Ltd. Redeemable Software License agreement.ou're gonna have a bad time. This is thanks to a bunch of units defined in
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

## SVF -- Serial Vector Format

Serial vectors are a great idea. If your designers implement them right then
you can colapse functional testing and focus on a simple interface. If you know
a bit about yoru interface you can create powerful functional vectors without
bothering to simulate. SVF was designed as an industry-standard interchange
format for serial vectors. There's also a Xilinx variant that's worth a look.

## Protip: If you're thinking of changing a group definition, don't

This can screw you in a number of ways. You may have forgotten how the group
was used in timing or levels. You may have forgotten how an equation-based
group is based on the group that you're changing. The ASCII tools may have
helpfully used a group definition for you in some convenient but utterly
inappropraite way. Easier to just make a new group.

## Quick Script: dfgp-be-gone.py

Get rid of troublesome groupings. Flatten groups used in timing, levels and
testmethods. Adds comments to remind you what groups were previously used and
what pins they contained at the time. Add to Antikc repo.

## BYOTE: Build your own Test Engineer

Develop a wiki/youtube course for interns and recent college graduates. Create
an industry partnership with Advantest, independant labs, employers large and
small to pair mentors with noobies for 1-2 months.

Advantest contributes a SmarTest license for life to each new TE. Gains a new
engineer supporting their platform.

Companies contribute a paid internship and test time (if they have testers) and
get access to the network of mentors and new TEs for hire.

Mentors contribute mentorship and wiki content. They get access to the network
of menthors and new TEs for career advancement.

## Tip Line (Rage against the NDA)

What's your salary? Stock options? Are you looking for a better offer? What did
you pay for a loadboard? Test time?  Probe card? Wafer sorter? Vector
converter? And to whom? Know of an open req? Ever bought a tester? I'd be
fascinated to learn the terms? Got an axe to grind? There's a spinning wheel
bellow, perfect for grinding axes. Share as many or as few details as you want.
Lie, defame. I don't care.  Are you a vendor and want to tip what your charge
for goods and services. Do it and you'll get a link. Your tip my be featured in
a future post.

Post anonymously (or nonymously) the dollars and cents of the industry.

Tips on posting anonymously:

* Use private browsing mode
* Don't post from your work computer (or any computer on your work network)
* Post using your phone from starbucks
* If you must post at work, use your phone and make sure wifi is off
* Create an internet avatar if you want to speak semi-nonymously (but be sure
  to cover your tracks. Don't sign up for your fake e-mail account using your
  real e-mail account)
* Use Guerilla Mail.
* If you want me to know your identity but not the internet, send me an email
  with the subject "KEEP ME OUT OF THIS". I'll qutoe you as "someone I trust
  but who shall remain nameless."

Feel bad about giving the finger to proprietary, NDA bullshit? Don't. Markets
run on information. Take a stand for free speech and free markets! You're doing
God's work!

One thing I will guarantee: No anymous tips are coming from me. I'm just giving
you a space to be heard. If I want to say something I will say it nonymously. -
Michael Fox, Test Engineer

## Ask a Probe Card Vendor

Try Luis at Probe Logic. Contact SV probe too. XY coordinates, pad material
(lead-free or leaded, gold, copper or tin), pad size, probing temperature. 

Ask about pricing formulas.

## How do you value stock options? Restrited stock?

## Spreading the word

LinkedIn, Twitter, Tubmlr, Facebook, E-mail subscription, Reblog (links
appreciated).

## Quick Script: Golden Device

Bring back the golden device feature but this time with arbitrary wave tables.
Set failing cycles to 0, 1, invert or X. Support SCAN_TEMPLATE.

## Licensing

Begin with a rant about how licensing wastes a lot of time and encourages
customers to invest in license optimization rather than readily adopt new
features. How would I do this better.

A tutorial on license optimization.

How does licensing work in the real world for independant labs? OSATs?
Tester-owning companies?

## Rant: SmarTest Should be Free and Open

Communist rant about owning the means of production and how can you expect
people to invest their careers in your technology if you extort them for tools?
Suggest giving free licenses to individual test engineers and sharing more
source code and being clear about how currently shared source code such as,
examples and templates, is licensed for sharing.

And it should be distributed as a VM. And all the documentation and images
should be on the website with minimal fuss?

SmarTest used to be free (I think. It was for me anyway.). Then some brilliant
person come up with the idea of nickle and diming. Test engineers have been
getting older ever since.  This is eating your seed corn. Mmm, delecious seed
corn. And to what end? A couple of bucks? Promoting your lousy training
courses? Classifying and channeling your customers? Keeping your competitors in
the dark? (They can easily check your shit out at an independent lab anytime
they fell like it.  Duh. To their credit, they're not copying your bad ideas
too much.) Marketing? (People will volunteer their information if you let
them.) It doesn't seem worth it.

A photo essay on the box.

Don't get me started on the bugs that persist for decades.

Given the stack of open-source technologies SmarTest is built upon, have you no
shame whatsoever?

Point out that I'm possibly over the line with what I've put on github already.
Give a thourough reading of my Advantest license agreement.

## Advantest Nees a Public Bug Tracker

SmarTest is bad and you should feel bad. Ascii tools? Seriously?

Don't want people to know SmarTest is full of bugs: HEY PEOPLE, SMARTEST IS
FULL OF BUGS! BUGS THAT HANG AROUND FOR DECADES!

(Insert graphic of someone with cotten in their ears or an osterich with its
head in the ground.)

Visibility fixes bugs. Writing robust code is hard. I have enormous sympathy
for the fact. But listening is easy. I have no sympathy for willful ignorance.

Please let me upload crash reports. (apport) Pretty please?

Now that they know, wouldn't you like a transparent process where people can
tell you about the bugs and track progress fixing them?

## Advantest Should Write a Vector Converter

Or buy one. How have you not?

## The least you shoud know: RegEx Tutorial

## Taking Vim to a Vector File

* gzip support
* binary data support

## Feature request: Parsing Errors

When loading a pattern master file, tell me which pattern failed loading, please.

ISE:tmp/pattern-master-failed-loading.png

## Feature request: Document ui report socket

## Feature request: Document event datalog socket

## Bug Report: Error Map Messes with Tester State

## Bug Report: Error Map, etc, Sucks with MultiportAny

## Bug Report: Align Display Gone from Vector Editor in 6.5.4

## HOWTO: Use Old Blue Vector Editor in 6.5.4

## Bug Report: Old Blue Vector Editor Hates DPS32

Crash.

ISE: tmp/old-blue-hates-dps32.txt

## Fix pasting in Vim under RHEL5

Middle-click pasting and vim paste registers don't work right under RHEL5.

## HOWTO: Use image magick to quickly capture something on the display

## Bug Report: Scan Vector Editing Goes from Bad to Nonexistant

## Bug Report: RegEx for Testmethod name 

## Vim: Make your command like behave like Vim

set -o vi

* search: /
* move: hljk
* find letter: f
* jump words: b, w

## Program bugs go to /var/opt/hp93000/soc/prog_bug_log

Interesting session stuff goes to /var/opt/hp93000/soc/common/tmp

* eclipse_sock_:1234 -- probably good for something "No such device or address" seems familiar
* xoc_sessionmanager -- something to do with running multiple smarTest sessions and figuring which one this terminal has.
* ApiNamingSvcLog

/var/opt/hp93000/soc/common/tmp/93k.asdf/

* ReportFile -- It's the UI report! Sweet!
* DataCollection -- tail -f DataCollection | strings -- the binary datalog is this easy to trap -- owned by process /opt/hp93000/soc/pws/bin/ess
  running /opt/hp93000/soc/pws/bin/ess -> bind: Address already in use. A fatal error was encountered in the ess (Event Stream Server) meaning datalogging is no longer possible "restart SmarTest and contact R&D ifthe problem persists." Contact R&D -- wish I could.
* Many more temporary files to research. Use fuser, lsof to see who uses what


## Bug Report: UserFlag corruption

## Bug Report: Leaky plugins easy to destabilize system

## Searching Mega / Trackers for SmarTest

## Defeating flexLM and other "node locking" methods

Also, time-based methods.

## Loadboard design: Use DPS32 First

## Protocol-Aware Testing

## File Naming and Directory Structure

## Next to My Tester

* Power Strip
* Multimeter
* Spacious desk
* Oscilloscope (200 MHz)
* Ethernet (or a wifi AP on the desk)

## Expressdata

## Open Source Software

* Octave -- desk calculator

## Frequency Test

Oh great. They made it worse. Now instead of using the error map you get to setup a vector variable. Also there's the PPTIA which might be the way to go.

## Rant: Parameter Documentation in New Standard UTMs

## Files

* .technology
* license

## Rant: Licensing

* Have to restart / reload to play with it
* Stupid language
    * Cutting individual pins out of ranges
    * "Channel 10110 specified twice" -- why not just let me specify twice and take the last? So much simpler
    * Why not just let me specify one feature
* Assigned to pin number rather than flexibly to pin names
* And why don't you tell me when changing device that the license/model mismatches. You wait to complain until I go to load my pin config you son of a bitch.
* Why do I have to name exact hardware? Just name the minimum PS400 and don't fuck me if there happens to be PS3600. Every time I change testers I have to tune this shit.
* Something you truly can't do offline.
* Here's an idea: Why don't you generate a model file for me based on what's actually in the tester?

Change device is fucking slow. I typed this whole article while waiting to change one device.

DFPN - Digital I/O channel #11504 for pin 'SPI_CLK_O' has mismatch between model/license file and installed HW. Well, what's the fucking installed hardware?

## Bug Report: pptia_tml.PptiaTest.Frequency Doesn't bother to Connect

## Bug Report: pptia_tml.PptiaTest.Frequency ReportUI in MHz but Limit Value is in Hz which is confusing

## Bug Report: Select Pattern list includes sub-patterns (per-port patterns) which I can't actually select

## Bug Report: Can't enter a "Insert Floating Testsuite" without pass/fail branches

But you can "Convert to Run Node". Just keep in mind that you won't even see
the option in the right-click menu until you ctrl-clk the testsuite to select
it along with it's empty pass/fail branches.

## TODO

* Github Antikc repo with submodules for other repos.
* Review some vector converters

## BYOT: VXI, PXI, AXIe -- Backplanes

The tester industry has levels just like the PC industry. 

## BYOT: ADATE207

http://www.analog.com/en/other-products/automatic-test-equipment/adate207/products/product.html

What's the replacement. Semiconductor industry is getting a bit secrative in
its old age.

Price: $73 ($18.25 per pin)
Release date: circa 2007

Compared to the specs of the PS400 digial pins, it's pretty-much identical.
With x2 pin multiplexing, it sounds a lot like PS800.

![Adate207 is not recommended for new designs](/images/adate207-not-recommended-for-new-designs.png)

## Testfloors

ISE, EAG, STS, GlobalTest, Qualcomm, Broadcomm, Rambus, nVidia

Interesting how companies that run a testfloor for development -- or even
production -- of their own product provide a much nicer working environment
than the any of the independent labs. Things like big desks, debug equipment
(oscilloscopes and the like) ready to go; no lab coat or booties required; you
can even drink a Coke while developing your test program in Broadcomm's loading
bay. Something about incentives.

## BYOT: Analog Device's ATE Brochure

This
[Analog Devices marketing brochure for Automatic Test Equipment Solutions](http://www.analog.com/static/imported-files/overviews/ATE_BROCH_FINAL_02_08.pdf)
actually surprised me. It gives a succinct overview of the components you need
to build an ATE like the hp93k. There's a picture of a big VXI-rack tester with
the Analog Devices log o emblazened on it. I guess I shouldn't be surprised
that ADI, a major Integrated Device Manufacturer who supplies devices to the
ATE market would build testers for their own use and maybe for some vertical
integration purposes.

## Vimwiki

It's an excelent product plus, what I have in mine.

## New JTAG for 2013: IEEE updates the spec

Finally, standardizing the internal registers. (Why didn't you do this in the first place?)

[JTAG Group homepage](http://grouper.ieee.org/groups/1149/1/)

IEEE 1500, IEEE 1801, IEEE P1687

## ntk.vim

"Download/Upload" Wavetable, Equations, Specs etc as provided easily by firmware.

Transform formats to Python / Lua

## BYOT: Test Evolution

[Test Evolution](http://www.testevolution.com/)
occupies a middle layer in the tester industry. 

## Things you should never do

In the year 2000, proto-blogger and my hero Joel Spolsky posted what he
considers to be his best ever blog post: 
[Things You Should Never Do, Part I](http://www.joelonsoftware.com/articles/fog0000000069.html)

> They did it by making the single worst strategic mistake that any software
> company can make:
>
> They decided to rewrite the code from scratch.

Joel was talking about Netscape but he may as well have been talking about the ATE group at Agilent.

OpenTest is an international trademark registered to Agilent Technologies.
Interestingly, I can't find a single other reference to the product that this
valuable trademark represents.

Maybe SmarTest isn't so bad after all. In fact, most of my complaints regard
throwing away of perfectly servicable interfaces in favor of worse ones that
languish for years. (Looking at you vector editor in smarTest 5.)

## Let's Buy Some Used Test Equipment

## Sweep Faster by Caching Timing Sets instead of SVLR

## Mutiport -- Sequencing Groups and Phase Lock

## Email service with

Send posts or reruns daily to keep up engagement.

Not sure how I feel abot all of the companies trying to engage me. I'm already
getting daily drops from Mentor Graphics, JEDEC, Synopsis (but interestingly,
not Advantest! Miss you Go/Semi.)

## Arbitrary Limits

Reading the "SmarTest character and number limits". Which limits are
reasonable. (Hint, only ones that are absolutely enforced by hardware and for
which no software hashing method could be used to work around.) Which should go
away?

## My Resume

### Experience

I've spent over a decade battling the hp93k semiconductor tester.

Dealing with Firmware Commands, TestMethod C++ APIs and dozens of
mini-languages. Using Python and Vimscript to work around misery and
weaknesses. Using Open Source to fix problems.

### Dream Job

**CTO Advantest**

I'd like a chance to finally fix the overarching problems with the platform.
Meanwhile, I'm blogging, bug-fixing and working around them one-at-a-time.

Other than that, if I could keep doing what I'm doing and not leave my house in
Pleasanton, CA too much, I'd be happy.

### References

Who needs references when you have [a blog](http://antikc.com) and a
[Github](https://github.com/gitfoxi)?

### Contact

Email me: m@antikc.com

### Shameless Keywords

hp93000, V93000, pinscale, SoC, ATE, Automated Test Equipment etc.

## Using NOOP to comment your firmware command files

But will SmarTest save them? Probably not.

## Linking to ASCII tools binaries to borrow VECC

libaldc

The funny part is that compressing the link (transparently) might actually do
some good in improving tester performance while using standard LZMA-type
compression for optimizing storage.

The bulk of the waiting for vector data to download is for scan patterns which
aren't especially compressible. If a vector was compressible, you would do
better to use the RPTV and other sequencer programming to compress its
footprint in the tester memory. Because ALDC only compresses what's on disk and
going over the fiber-optic cable, it doesn't save you any tester resources.
Since it is slow, I would recommend not compression scan patterns -- it's a
waste of time.

This all seems dumb to me, but hindsight is 20/20 and I didn't show up for the
meeting (my fault: I was in junior high).

ALDC is mentioned twice in the documentation:

* CTRL (PCI-E based) -- There's some diagnostic tests for the control board
  which is apparently where the fiber optic interface enters the tester. This
  must be where an ALDC chip designed to live in a tape drive has taken up
  residence after hard disks were invented.

* use_vecc -- paramater for the STIL reader telling it to compress patterns
  using libadlc when converting.

Research suggests there's two different ways compression can be done:

* ALDC -- This is what I'm interested in as it seems to apply to everything
  from C400 to PS3600.

* LZW -- This is for the hp83k (I think)

And the files do come out differently depending on whether you're targeting SM,
VM or UMM memory, but I think that's due to differences in how the uncompressed
data is padded and not in the compression algorithm itself.

If I were designing a tester today I'd compress the link with some fancy
hardware compression. That still makes sense. But for on-disk storage I would
specify only standard compression. The LZMA you get with 'xz -1' is excellent
and fast. This way, the CPU decompresses data, saving disk and network traffic,
then the CIC card hardware compresses it using something like ALDC (probably
something better available by now) and finally the tester's control board
decompresses and processes any data flying across the wire (or fiber as the
case may be, but fiber is not a choice I would make in 2013 -- better look at
some PCIe or USB-based copper serdes).

## How (not to) handle binary data over a socket

BSON is an example of binary done right. JSON and YAML have good support in
their own way. The key is escaping, out-of-band messages, not fixing record
length.

## Worst-Case Scenarious in API Design: Numbering timing and levels sets

Very bad for modular development. Hampers cooperation and fosters crappy
scripts to work around the numbering collisions (Everyone wants Equation Set
0).

Namespaces. Use names. I get there's a hardware limitation. Try harder to hide
that from me.

## Thanks for not stripping your binaries

## Submissions Guide

* No Cheerleading
* Tell like it is
* Name names (and numbers)

## Modeling the tester as a big box of state

Tester + Loadboard devices + SmarTest + My Code + DUT is a massive
N-dimensional object flying through finite state space. How can programming
models benefit from this view? (Other interesting factors are temperature, and
whether all of the equipment is in good repair.)

Unfortunately the states of these things are like a mountain of global variables that will influnce your tests in varius incomprehensible ways.

Side-effect-free programming: How to keep one testsuite from fucking with
another by changing the state of the tester. (Or allow it as the case may
require.) Monads.

DUTs introduce state. Sometimes reset doesn't mean what you think it means. In
a bad implementation some registers and memories can start in a random state.
The reset pin might preserve some values from before when it was asserted. This
is done for someone's convenience. But for the test engineer it may be required
to ground Vdd to make sure the damn thing fogets.

A problem is that the tester encourages economy of resources through sharing.
Otherwise, you'd want a unique state going into each test. Think about the
limitations on timing sets. What if a prior test SVLRs a spec and doesn't set
it back. How can you expect that (without any effort at all)?

Operating systems give programs the illusion of more resources than they have
and shield them from the underlying details. Operating systems protect programs
from each other while allowing clear channels for communication (which may
neverthess be source of instability and are best kept simple or avoided. Do we
need a Virtual Tester Machine? While we're here, could we make it multi-user so
several people could work on different aspects of the program at the same
(sliced) time? How about, every testsuite can assume the tester starts in the
same state (assuming a good DUT)? That would simplify integration a lot. At
some point we have to stop worrying about test-time reduction and think about
development-time reduction.

Why do we accept that we should optimize license usage and test time and keep
obsolete testers online forever because they're paid off. All at the expense of
engineering? It's akin to premature optimization. Do you ever really earn your
extra development time back? If you're too late to market then obviously not.
But what about the test time burned sitting staring some over-complicated
broken test program? I know this is convenient to Advantest's business model
that you should be profligate with expensive resources that they sell. But I'm
open to thinking about it. Markets are efficient and if we all use more testers
then, the theory says that there will be more testers produced with each one
costing incrementally less. That's the kind of thinking that helps everyone.

This points to an opportunity for Advantest: Deliver a product that reduces TCO
by being stable and robust though slower and less efficient and you'll sell
more of them. Especially to the degree that Test Engineers are sometimes asked
for their opinions on tester technology adoption, you may just have the wind to
your back with such an offering.

## conv_vector

Changes memory type of vector

Memory types: VM, SM, UMM
Targets: F330 (83k), C200 (everything up to pinscale), MCU (not sure what this is)
-compress -- compress the vectors. Or not!
-toascii -- dump waveform indecies of a pin

## LSB versus MSB-first in serial bitsrream

Like endianness but for bits instead of bytes. A JTAG surprise.

## ALDC is more trouble than it's worth

Adaptive Lossless Data Compression (ALDC) is used by the hp93k to implement the
binary compression format used in VECC vectors. The goal is twofold:

1. Speed communication between the workstation and tester.
2. Save disk space

Sadly, HP dropped the ball implementing it. As it turns out, ALDC slows
communication and eats more storage space than a more straightforward approach.
Ouch.

If ALDC had been properly implemented, you never would have heard of it. ALDC
is optimized for hardware implementation. It is implemented by two matching
chips, one on each end of the fiber-optic cable. In a straightfoward design,
uncompressed data passes through the compression path on it's way into the
cable and through the decompression path on it's way out. This is completely
transparent to the rest of the system. Endpoints sending or receiving just sees
the uncompressed data and perhaps notice that throughput is higher than the
bitrate of the optical transciever allows for itself.

But then someone got a bright idea: Since the bulk of communication between the
workstation and tester is vector data, and since vectors take up a lot of space
on disk, why not program the computer to compress the data at the time of
vector conversion, store the data compressed (saving disk space) and simply
implement the decompresser in the tester, while avoiding putting a matching
compression chip on the workstations fiber-optic interface card (CiC, as they
call it). Look at the savings:

* Instead of two compression/decompression chips, now you just need one decompression chip.
* Instead of using standard gzip to compress data on disk, now it's already comprressed.

You get into trouble when you realize

* Scan data is not compressible and represents the bulk of the data in the system.
* The scarecest storage is not the hard drive in the computer it's the memory in the channel card. A useful compression system should be implemented at the pin.
* ALDC, while optimized for hardware implementation is extremely awkward and slow for a general-purpose processor. And since this data must constantly be compressed and decompressed to make your ASCII tools and your vector editor work, you end up with a slow online development environment and a massively slow and memory-hungry offline development environment.

## Idea: Compress VCD using per-pin time differentials and LZ4

A fast and simple approach which allows random access.

An excellent data compression blog from the author of LZ4: http://fastcompression.blogspot.com/

Gets into topics like inlining, data alignment, streaming, hashing performance ...

Fast longest-match search MMC: http://code.google.com/p/mmc/

Boom Rants: http://cbloomrants.blogspot.com/ Charles Bloom 

## Benchmarking vector compression time:

Tool, user, real, size, size%
v2b (no-compression), 144.6s, 147.2s, 808M, 100%
v2b -C (compression), 149.8s, 152.2s 97M, 12%
cat, 0.0s, 2.8s, 808M, 100%

Fast compressors:
aldc (v2b), 5.2s, ?s, 97M, 12%
lzo, 1.3s, 1.7s, 104M, 12%
snappy, 0.90s, 1.1s,  120M, 15%
lz4 -c0, 0.98s, 1.3s, 141M, 17%

Slow compressors:
lz4 -c1, 120.1s, 121.3s, 62M, 8%
xz -0, 26.3s, 26.5s, 49M, 6%
xz -1, 28.9s, 29.2s, 46M, 6%
xz -9, 501.4s, 503.2s, 36M, 4%
gzip -1, 8.2s, 8.5s, 66M, 8%
gzip -9, 447.0s, 448.1s, 42M, 5%

I caught xz -9 using 673M of memory at some point! Gzip -9 used almost no
memory. Is that because it's implemented in the kernel?

Estimate 5.2s CPU time for v2b ALDC implementation. It's the worst speed of the
fast compressors, but the best compression. There's no comparing the fast and
slow compressors.

I was pretty disapointed with `xz -0` which is advertized as faster than `gz
-1` and better than `gz -9`. Does not deliver.

Interesting that snappy dominates lz4 on both time and compression in this case.

Other:

lzjb node implementation was pretty slow and worst for compression.

Conclusion: Snappy-c should make a good start for my ALDC implementation.
