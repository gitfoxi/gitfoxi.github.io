---
title: "VTRAN vector converter review"
layout: default
---

# VTRAN vector converter review

## The Bottom Line



## Trip Report

### Off to a Rough Start

I'm pretty excited about VTRAN's website. They let you [download the software](http://www.sourceiii.com/support.php#downloads) and [download the user's manual](http://www.sourceiii.com/files/vtran/vtran_man.pdf) right from [the VTRAN product page](http://www.sourceiii.com/product-vtran.php)

Source III provides a nice little 
[form for requesting evaluation keys](http://www.sourceiii.com/support.php#evaluation-keys).
Unfortunately, the first time I filled it out, it gave me this friendly, though
unhelpful response:

![vtran-error](/images/vtran-sorry-you-have-faced-an-error.png)

I think it's a little too aggressive in validating my FLEXnet host ID. I had
entered my wlan Ethernet address. After deleting some colons I was joyous to
see:

![vtran-thank-you](/images/vtran-thank-you-for-your-interest.png)

But no evaluation key. I guess it can't be easy. That was 2:30 pm on a Tuesday.
In the meantime, I decided to flip through the user's manual.

### User's Manual


# Notes

Merging timing sets is not supported with xmodes. 

DVC apparently uses obsolete wavetable format, instead of the new physical waveforms required by smarTest 7.x

Is X8 supported? HX? PS3600?

Special XMODE section in Appendix D

Specifying an xmode for ts1 didn't work:

    tester_format = hp93000 -use_bus_names, dvc_file="tvfb.dvc", pin_config_file="tvfb.conf", xmode="ts1 4";

It ran without error but the DVC was still X1.

Says that it's limited to 32 state combinations for a pin in xmode but also says it supports xmode from 2 to 8. Pinscale should have the option of 256 combinations.

Multiport.

Does it give you .aic file or v2b command line?

After I get xmodes working with the xmode_map file I see that some wavetable entries distinguish between capital and lower-case z: `ZZZzzz11`

There doesn't seem to be a log file to give me insight into what it's thinking.

The pin-configuration file that it generates assigns all channels to 10101.
This is fine since you will have to assign to match your loadboard. But it's a
little bit useless if you want to use it pre-loadboard to see how signals look
in the waveform viewer. It would be helpful if it would increment the channel
numbers like it does the pad numbers.

    DFPN 10101,"1",(reset)
    DFPN 10101,"2",(rstint)
    DFPN 10101,"3",(iackmn)
    DFPN 10101,"4",(iacksn)
    DFPN 10101,"5",(inscl)

I thought adding this to `proc_block` would help:
    
    state_trans 'z' -> 'Z';

But I was wrong. Maybe this would work:

	state_trans bidirects 'z'->'Z';

Nope:

    Error: Illegal syntax in STATE_TRANS Command - line 24 (VTRAN-156)

I guess `bidirects` isn't a group name like `inputs` and `outputs`. Also curious was the lack of capital 'Z' in the vcd input or the avc output.

Anyway, maybe it doesn't matter. Have to go to the next stage to see if ascii tools will merge 'z' and 'Z'.

"Pad" vectors seem to keep expecting an output. I would prefer to see output states mapped to 'X' in these extra vectors. Instead of:

    R1   ts1 00111100000110zzzzzzzz00U; 4504
    R1   ts1 00111100000110zzzzzzzz00U; pad_vector #1
    R1   ts1 00111100000110zzzzzzzz00U; pad_vector #2
    R1   ts1 00111100000110zzzzzzzz00U; pad_vector #3
    R1   ts1 00111100000110zzzzzzzz00U; pad_vector #4

I'd like to see:

    R1   ts1 00111100000110zzzzzzzz00U; 4504
    R1   ts1 00111100000110zzzzzzzz00X; pad_vector #1
    R1   ts1 00111100000110zzzzzzzz00X; pad_vector #2
    R1   ts1 00111100000110zzzzzzzz00X; pad_vector #3
    R1   ts1 00111100000110zzzzzzzz00X; pad_vector #4

I thought this might list the pins in my vcd but no luck:

    $ vtran -pins vcd ovf_vcd
    Error: Unsupported canned reader format: vcd

This seems useful. The official excuse is that you won't get to an error in your .cmd file until that section happens. A better idea is to check the syntax before processing.

    $ vtran -check ovf_vcd_93k.cmd

This feature seems helpful, but I wish I could learn a lot more about my vector file and maybe create a template .cmd file based on it:

    $ vtran -vcd_mode ovf_vcd
    VCD
    
Vtran supports pipes for stdin and stdout, as it should. But here's a bug:

    $ cat ovf_vcd | vtran ovf_vcd_93k.cmd -stdin -stdout > out.avc

This appears to work:

    $ cat ovf_vcd | vtran -stdin ovf_vcd_93k.cmd -stdout > out.avc

But no such luck:

    $ cat out.avc

    VTRAN 9.6.2 (C) 2013 Source III, Inc. 
    Reading command file...
    Processing command file OVF_BLOCK...
      Using VREAD to read verilog_vcd formatted file ....

      verilog_vcd file successfully read.
      Original Vector File successfully loaded.
    Processing command file TVF_BLOCK...

    Formatting Target Vector File in HP83000/93000 format...
    Translation complete.  No errors detected.  Output in file: tvfb.avc

Surely this is the magic formula:

    $ cat ovf_vcd | vtran -stdin -stdout ovf_vcd_93k.cmd > out.avc

But when you look at out.avc, you'll see it's pasted the VTRAN masthead into your file:

    $ cat out.avc

    VTRAN 9.6.2 (C) 2013 Source III, Inc. 

    #
    # Converted by vtran version: 9.6.2
    # Date: Tue Sep 10 15:08:40 2013
    # Source file: 
    #

    FORMAT 
      reset rstint iackmn iacksn inscl insda mcs scs rad nregrd nregwr pclk rdb
      irqm irqs sdo;
    ...

Okay, workaround time:

    $ cat ovf_vcd | vtran -stdin -stdout ovf_vcd_93k.cmd | tail -n +3 > out.avc

Crazily, the bug goes away if you just use `-stdout` and not `-stdin`

We can use this to bring back the gzip feature, albeit with some akwardness:

    $ vtran -stdout ovf_vcd_93k.cmd | gzip -c > out.avc.gz



Can we convert back from timing/binary or timing/avc to vcd or stil?

The .cmd file syntax is tedius and I'd much prefer lua, python, regular-expressions, etc.

Vtran has many bugs. But source iii does offer responsive support
so if users engage them enough maybe this improves over time.

Also, your command files will have bugs and they will be tricky to debug.  I
can't think of an obvious way to improve this situation without access to the
source code or really without overhauling some things that are probably not
worth overhauling.

It's not clear whether VCD timing is derived from the signals, or a fixed
sampling time or if there's both options.

Bug: -gzip command does nothing. This should cause .avc to be gzipped (in my mind):

    tester_format = hp93000 -use_bus_names, xmode_map="+tvfb.xmap", xmode="ts1 8" dvc_file="tvfb.dvc", pin_config_file="tvfb.conf" -gzip;

But it does nothing and doesn't produce an error warning either.

# Irreducable bugs

The price of having the most features is a high one. Thanks to the concept of
Irreducable Bugs, the more complex a program the more bugs it's bound to have.
You get to a point where any bug you fix is bound to create at least one more.

Also, it's murder on the learning curve. There's a lot of features you don't
need to sift through looking for the feature you need.


# Arbitrary terminology:

* ALIGN_TO_STEP versus ALIGN_TO_CYCLE. What's a step? What's a cycle? They're the same thing, just that ALIGN_TO_CYCLE allows per-pin definition of sample offsets.
* OVF -- Original Vector Format
* TVF -- Target Vector Format
* Print On Change -- Like VCD
* Cycle-based -- Like AVC

# Arbitrary rules:

* Only one ALIGN_TO_CYCLE per command file.
* BIDIRECT_CONTROL has two completely different syntaxes. MASK_PINS has seven. Why not another way?
* Some commands apply to a select set of pins, others to all pins. Unclear why. MERGE_BIDIRECTS for example, applies to all pins.
* Up to 10 groups can be referenced in the format string -- very arbitrary limit

# Arbitrary syntax.

Sometimes it's surprisingly readable. Sometimes not so much.
Sometimes it cares what order you say things in, other times, no. Maybe you get
used to all the little exceptions eventually, but I haven't yet.

And then we tack on REGISTER, admitting that we have to work around what's missing by not having a real scripting language.

Useless new way to define a parser instead of regular expressions.

STATE_TRANS and STATE_TRANS_GROUP are separate syntaxes which could be combined recognizing that there's some pre-defined groups like INPUTS, OUTPUTS, BIDIR_INPUTS, etc

# Cool features:

* ALIGN_TO_SIGNAL - Adjust sampling of one pin to match transitions on another. This way you can translate in a protocol aware way.
* POIC - print on input change waits for the first change to avoid putting garbage at the head of the vector - could use an initial state definition and more specificity as to which input must change.
* VERILOG_TB - There's several vitual-tester products and maybe Vtran includes one bundled with its ability to create a verilog testbench from a test vector.
* HP93000 canned reader can turn an avc/dvc into a vcd. Cool, but incomplete. Doesn't do binary vectors and doesn't support all AVC syntax even. So, not totally useful for porting a program from HP93000 to another platform. To be fair, a complete solution would be maddengly hard to create. :(
* Flexible bus notation: BUS[1,5,3], BUS[16..0], BUS[16:0], BUS[16-0], BUS[16,15,14,13,3:0] are all handled correctly.
* Bus recognition: Of course, some ass-hat will always come along and start naming pins gpio_7_b, gpio_6_b -- again, you really need some regex support because you can't plan for everything an asshat will do.

# Lacks, Sucks

* Multiport
* Project organization
* ait, aiv, v2b -- ascii-tools automation
* Development process
* Random, confusing language
* Scriptability, API -- acting as a service to a user's program
* Intermediate logs to help debug the complicated flow
* Sometimes useless and confusing errors and warnings
* Often unclear in docs what's an input and what's an output. i.e. pin-config file
* Demands a lot of analysis and intelligence -- then turns around and doesn't respect your intelligence
* Not 93k focused -- missing binary vector output, per-pin compression, duplicates syntax for timing and wavetables (there is SYSTEM_CALL if you want to implement it). Prints a pin config file if you specify TESTER_CHANNEL is almost more work. Among the wealth of examples, few apply to 93k. Among output timing is RZ and RO but no SBC.
* Yet another standard (intermediate format) and a poorly-documented one at that. See XKCD on standards TODO.
* Command-line override of .cmd file for easier batch scripting.
* Many warnings should be errors (-terminate_on_warnings or TERMINATE_ON_WARNINGS is highly recommended)
* Should have a global configuration block instead of throwing all global options into OVF block

Vtran tries to address every special case because it is the
everything-to-everything tool. If it were just a VCD to 93k tool then it would
be perfectly reasonable to demand that the VCD file adhere to certain
conventions. Having conventions makes the untractable world of choices
tractable by limiting what you can do. It also requires some thought and work
on your part, and potentially time-consuming re-simulation when you get some
little thing wrong -- so there's a real tradeoff here.

# Ideas

You could generate test vectors by recording a chip's activity using a logic
analyzer. My buddy told me his company was doing that. Seeing vtran's explicit
support clues me in that this is a real thing.

You can translate logic analyzer output in to simulator input. So vtran is
useful for more than just creating ATE test vectors. You could take a stimulus
and run it through simulation for debug. I wonder how practical that would be
with an SoC which can take quite a while to get to a particular state. Fast
simulators would be needed.

STIL WGL viewer by converting to VCD then using gtkwave.

