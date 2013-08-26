---
title: "Bug Report: TestMethod Namespace Pollution"
layout: default
---

# "Bug Report: TestMethod Namespace Pollution"

In which I submit unsolicited bug reports for the hp93k.

## Summary

- Product: SmarTest
- Version: 6.5.4 & all versions containing the TestMethod API
- Platform: RHEL3, RHEL5, HPUX (all)
- Module: TestMethod API

## Details

`#include <testmethod.h>` sucks in a large number of `#define`s for the purpose
of units interpolation. This enables an ostensibly cool feature where you can type:

    double stim = 10uV;

And it's as if you had typed:

    double stim = 10e-6; // 10uV

This is thanks to the line in `MapiUnit.h`:

    #define    uV        *1.000000e-06
    
But wait -- to an experienced C programmer, `10uV` looks like a syntax error.

Worse, `MapiUnit.h` goes way too far and defines replacements for 120 short,
common sequences of letters which an unwary programmer will accidentally select
to use as a variable name. The `#define`s create a large number of 1-4 letter
keywords right on top of prime real-estate for quick temporary variable names.
Here's the full list:

    A bps cnt CODE dB dBc dBm dBm0 dBr dBrn dBV deg degC degF degk fA fdB fHz
    fohm fOhm fs fsec fV GA GdB GHz Gohm GOhm Gs Gsec GV Hz IRE J kA KA kdB KdB
    kHz KHz kOhm Kohm KOhm ks Ks ksec Ksec kV KV LSB mA MA mdB MdB mHz MHz mJ
    mohm mOhm Mohm MOhm ms mS Ms msec Msec mV MV mW nA ndB nHz nJ nohm nOhm ns
    nsec nV ohm Ohm pA pct pdB pF pHz pJ pohm pOhm ppm ps psec pts pV pVs rad
    rpm s S sec Sps uA udB uHz UI uJ uohm uOhm us uS usec uV uW V Vp Vpk Vpp
    Vrms W

A C++ compiler is unhelpful in diagnosing a Macro-name collision. For example,
if I say:

    int uV = 10;

Then `g++` will complain:

    defineerr.cpp:5: error: expected unqualified-id before numeric constant
    defineerr.cpp:5: error: expected initializer before numeric constant

Which tells me on which line things went wrong, but not much more. And it's not
just my code. If I `#include` any system or library header files after
`#include <testmethod.h>` I have to hope that the library doesn't make use of
any of the 120+ new reserved words.

## Short-Term Remediation

Programmers are advised to:

* Print the above list of hot-lava identifiers on a card and tape it to every SmarTest workstation
* Avoid using any variable names between 1 and 4 characters in length
* Place all `#include`s at the very top of the file, above any hp93k headers

## Long-Term Remediation

At this point, fixing the problem will require fixing all code developed under
the TestMethod API. It will also trigger a review of example-code and
documentation. Since the SmarTest developers are good at making parser/emitters
to port code every time they decide to dynamite their API and start over
building a worse one, I think they can do it. But it's a big, tough job which
will inevitably create further unanticipated problems.

The automated code porter could change all `#define`d units to be proceeded, by
double-underscore. For example `uV` becomes `__uV`. Another strategy would be
to kill off `MapiUnit.h` and move the `#define`s into the TestMethod sources as
necessary. So, at-least, it's clearer what's going on, and it gives a hint to
programmers about how they can create similar magic, or not, depending on
whether they want to accept the tradeoff.

In the long run, if features like this are considered highly desirable, then
it's best to move to a programming paradigm that is more suitable to
Macro/Meta-programming. C and C++ are just too low-level to comfortably absorb
this concept (and many others embraced in the TestMethod API). Python is a
solid, obvious, choice. 

## `<rant>`

This sort of bug points to a larger problem in the philosophy of SmarTest,
namely that *SmarTest values a false sense of user-friendliness above all else:
Quality, Stability, Coherence, and Actual Usability consistently take a back
seat*.

Come on guys.  Your users aren't n00bs and they don't need the hand-holding.
(Even if it was helpful, which it's patently not.) They are technical
professionals who posses the skills to regularly navigate the minefield of a
massive, buggy platform that you foist upon them.

This misguided attitude leads to the mess of unnecessary Graphical User
Interfaces, Domain-Specific Languages, Force-Fed Object Orientedness and
Medusian APIs that is SmarTest today.

Next time you decide to put a bullet in SmarTest and start over, consider that
the way to true user-friendliness is to do what everyone else is doing. The
further you depart from the methods used throughout this and related
industries, the harder your platform becomes to build, teach, validate and
maintain. (And, the harder it is for your customers to hire and train test
engineers -- leading to an ever shrinking pool of technical experts supporting
your platform.)

*Do what everyone else is doing and you don't have to re-invent any wheels, nor
train people how to use the new wheels.*

There's a wealth of software development technologies that have grown up around
the Internet and attained popularity because people like them and use them
voluntarily -- not because their dog-shit platform forces
them to.

Consider adopting already-existing open-source libraries, rather than creating
your own.  The only reason I can think you're not doing this is that you don't
want to have to open-source portions of your own code.  But honestly, you have
nothing to fear from your competitors benefiting from your hard work: The would
be doing themselves and their customers a disservice to adopt your crazy
methods.

Consider ditching decades of in-house "invention" in favor of exemplary
projects from the rest of the world.

Consider that less is often more.

Consider accepting bug reports through your website. 

`</rant>`
