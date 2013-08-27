---
title: "Coming Soon: Vector Converter Reviews 2013"
layout: default
---

# Coming Soon: Vector Converter Reviews 2013

Converting a vector from EVCD, VCD, WGL or STIL to use on the hp93k can be a
fraught experience. Sure, you can write your own one-off scripts to cyclize
time-based formats into AVC (which stands for ASCII Vector Carnivore ... I
guess they just needed a third letter for the file extension). 

Scripting can be fun
but also frustrating because different patterns coming from different
environments will surprise you with their variety and variation upon supposed
interchange format specifications.  WGL and STIL are already cyclized and you'd
think this would improve the situation but both formats suffer from
specification bloat making for truly massive parsers which can never hope to
cover all the demonic variations hastily-developed EDA tools will throw at you.

At some point, you might just want to pony up for a commercial vector
conversion tool which comes with years of adaptation to support all the EDA
vendor's flavors of vector output and all of the ATE vendor's flavors of tester
input. 

But choosing a tool and learning it to proficiency is its own challenge. Most
test engineers have only worked with one of the several options and there's no
independent reviews on the Internet -- until now.

On your behalf, dear reader, I will request an evaluation license for:

* VTRAN - Source III
* Tester Data Link / VCD2ATE - TestInsight
* V2SOC - Evans Analytical Group (EAG)
* Verifier - Simutest
* VectorPro / VectorPort - Test Spectrum
* Test Development Series (TDS) - Test Systems Strategies (TSSI)
* VelocityCAE - AllianceATE

## Criteria

My reviews will be unbiased and independent. I'm a working test engineer and
not associated with any of these companies.

I'll look at factors that matter:

* Usability
* Format support
* Installation
* Cool Features
* Pricing
* Tech support
* Quality documentation
* CPU and memory performance
* Bugs

I will review the interesting features of each tool. Then I'll benchmark their
performance. Finally, some independent QA: I'll do my best to crash them.

## The Tools

Before I evaluate, I'd like to spread a little hearsay based on my limited
experience and a cursory skim of the tool's websites:

### VTRAN

[VTRAN](http://www.sourceiii.com/product-vtran.php) offers the best website by
far (pity about the ALL-CAPS name, though.) They're also doing a bang-up job at
Search-Engine Optimization. Just Google "hp93000 vector conversion" and check
out all of the top hits.

They put their User's Guide and several examples up for download. It's a very
good sign when a company is willing to let you learn about their product,
independently, without the company of a salesman. Opening the [VTRAN User's
Guide](http://www.sourceiii.com/files/vtran/vtran_man.pdf) I see that it's
dated "April 2013". I'm writing this in August 2013, so that's a good sign that
the tool is under active development.

For hearsay's sake, VTRAN is probably the best known tool. Although I've never
used it myself, several colleagues have recommended it and when I give patterns
to the consultants at [ISE Labs](http://www.iselabs.com/) to bring up, this is
what they use for conversion.

The downside of familiarity is that I already know something of VTRAN's
quality from my interactions with ISE. (Although I can't say much about other
tool's choking habits, that's just for want of experience, something I plan to
rectify.) On one occasion ISE had to upgrade their computer's memory
because VTRAN barfed after grinding away for several days at a large ATPG
pattern. On another occasion there was a completely unhelpful "parse error" on
a STIL file, which was only fixed by rerunning and dumping it as WGL. And, on
yet another occasion it got tripped up on my pin names. Apparently VTRAN likes
to assign internal pin names ending in `_I` and `_O` for bidirectional pins.
Unfortunately, this is exactly how I had named my pins. Through some effort,
all of these problems were worked around, but it was a hassle.

### TestInsight

[TestInsight](http://www.testinsight.com/products/design-to-tester-conversion/tester-data-link.aspx)
is another well known player. I've spoken with their sales about a different
product and they were very nice. I learned that they created the STIL Tools for
93k that Verigy/Advantest markets. So, if you're using STIL Tools, then you're
already familiar with TestInsight's work. I also learned from the salesman that
TestInsight is the only vector tool recommended by Verigy.  Funny though,
I've never heard that from anyone at Verigy. Anyhow, if Verigy/Advantest knew
anything about vector conversion they'd write their own tool and include it
with SmarTest. Take it with a grain of salt: salesmen are generally full of
shit.

From their website, it's not clear whether the product I'm interested in is
[Tester Data Link](http://www.testinsight.com/products/design-to-tester-conversion/tester-data-link.aspx)
or
[VCD2ATE](http://www.testinsight.com/products/design-to-tester-conversion/vcd2ate.aspx).
(Again with the all-caps naming. Must be a thing.) I'll probably just ask to
take a look at both.

Beyond that, I'm disappointed with TestInsight's web site. There's not much in
the way of documentation or even detailed information. Just claims like "Rich
Tool Suite" and "Allow multi-port". This is why I must do a review.

### V2SOC

[V2SOC](http://www.nanoisi.com/product_subpage1.php) -- again with the all-caps
-- is the last tool that I know much about. In fact, I used to work on the
code back in the day. It was an in-house tool for a company called Berkeley
Consulting Services. After I left BCS it was gobbled up by Nano Integrated
Solutions which was in turn a tasty meal for Evans Analytical Group.

V2SOC was difficult to commercialize. Every time we got a new client I had
to tweak the code. This points to the fundamental problem for commercial vector
converters: **It is all-but impossible to deal with every broken vector file
some low-rent simulator spits out.**

Looking at the web site is discouraging at best. Copyright Nano ISI 2007.
Supports "next generation Pinscale" and "BIST ASSIST" both of which are
yesterday's news. I have a colleague (another former BCSer) who requested a
quote from them as recently as last year and balked at the price and the
limitations on the evaluation copy. If it weren't for that, this website would
convince me that EAG had put V2SOC out of its misery.

Still, I must look up my old girl, V2SOC, for old-times sake.

### Verifier

[Verifier](http://www.simutest.com/prod_ate_ready.htm) from Simutest is almost
unheard of by me. Except that my boss tells me he has used Simutest a long time
ago and he was very happy with their work. Verifier's web page is Copyright
Simutest Inc, 2008-2009. That's more recent than V2SOC, but the presentation is
even worse. 

Though the website doesn't tell much, there is a link to a
[datasheet](http://www.simutest.com/images/Verifier_Tech.pdf) which is a bit
more informative. It looks like Verifier has tons of features. This may or may
not be a good thing. I've noticed there's a trade off, between number of
features and the quality of any given feature. The datasheet has screenshots
which remind me of my first Unix experience, running FreeBSD in 1994.

I must say, I'm excited to look at a tool that "Displays simulator logic
waveforms" and "Generates optimum timesets". But I do not expect to be thrilled
with the GUI. A good text-based interface beats a bad GUI any day. And a good
GUI is almost unheard of in the EDA world.

### VectorPro / VectorPort

[VectorPort](http://testspectrum.com/home/solutions/tools/vectorport/) is a
random that I only know of thanks to Google. It claims to support "Verigy 93k"
and "WGL or STIL input formats". The related
[VectorPro](http://testspectrum.com/home/solutions/tools/vectorpro/) looks like
it's their VCD tool.

The web page is okay. At first, the screenshots had me worried that these are
Windows-only tools. But the copy assures me that it supports "Linux (kernel 2.6
and higher)" so that's good.

Keeping track of the copyright dates, VectorPort's web page was touched in 2010
-- so, that's this decade at-least. GUI-heavy tools give me a bad feeling, but
I'll try to swallow my prejudice and give an even-handed review anyway.

### TestDeveloper

[Test Development Series](http://www.tessi.com/index.php?option=com_product&task=''&obj=view&id=12&name=Test Development Series)
from TSSI claims to support "90 tester models". I will be
happy if it supports just mine.

Apparently TSSI won an award for "Best in Test" from "Test & Measurement World"
in 1991. And they haven't updated their website since.

In all seriousness I have heard of TSSI. They have the dubious distinction of
owning the WGL standard. I feel like I saw a spec for WGL some years ago, but
that might be a false memory. Judging from how WGL has been implemented across
the industry, no one has ever seen the WGL spec. Really, it's a shame to
promulgate a standard and then hide it. Sure, publishing might help your
competitors, but it will also help your cooperators, and aren't standards about
cooperation?  STIL was created in direct response to the closedness of the
inexplicably popular WGL. So I blame TSSI for the failings of both WGL **and**
STIL.

And yet, if there was one company that you'd hope could convert WGL files to
use on the hp93k, TSSI is that company, so I'll have to swallow my rage and
give them a try.

### VelocityCAE

[VelocityCAE](http://www.velocitycae.com/) from AllianceATE is one that I
almost missed. Their search engine optimization is terrible. I couldn't find
them on Google at all. I just remembered that years ago, when I was working at
Agilent, these guys had a cubicle and they were supposedly working on a Python
vector converter.

Luckily the name AllianceATE is somewhat catchy and I happened to remember it.
A visit to their website shows that they do indeed have a commercial vector
converter.

The VelocityCAE website isn't quite as good as VTRAN's, but it's easily the
second best in the group. They've posted screenshots (GUI, yuck) and their
[User's Guide](http://www.velocitycae.com/docmanager/files/VelocityReference.pdf)
is online. So that's encouraging. I know the guys who made it are consultants
focusing on 93k, so that, plus the Python thing plus the name Ken Meade (which
I've heard uttered by the Verigy consultants in a hushed, respectful tone)
makes me feel pretty optimistic about this one.

## Suggestions?

So that's my plan. It's called **Vector Converter Reviews 2013** so I have
until December 31st to finish. Subscribe to my [RSS](/feed.xml) or check back often.
I'll be posting updates as I go.

Meanwhile if there's a vector converter, or other hp93k-related tool that
you're curious about or that you want to tell me about, or if **you** want to
join the fun and write some reviews, let me know in the comments.

**Update: Added VelocityCAE**
