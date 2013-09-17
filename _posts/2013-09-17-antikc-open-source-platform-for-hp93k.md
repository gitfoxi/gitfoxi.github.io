---
title: "Antikc Open-Source Platform for hp93k"
layout: default
---
# Antikc Open-Source Platform for hp93k

The hp93k platform is aged and creaky and that makes me sad. Often I want to
use a new tool -- new in the sense that it became popular within the last
decade -- but RHEL5 doesn't have it, let alone RHEL3.

For example, I like to use [Git](http://git-scm.com/) to version control my
device directories. I like to download new Python libraries like
[Parsley](https://github.com/python-parsley/parsley).
To get the hot new codes, you need Git to access [Github](https://www.github.com)
and it's assumed that you have a reasonably recent
[version of Python](http://python.org/) like 2.7.5 or 3.4.0 with
[Pip](https://pypi.python.org/pypi/pip) to install dependencies and
[Virtualenv](https://pypi.python.org/pypi/virtualenv) to keep things organized.

RHEL5 ships with the ancient Python 2.4 and RHEL3 is much worse with Python
2.2. Python 2.2's final release was in 2001. Python 2.4 was finalized in 2004.
New packages don't bother testing against anything pre-Python-2.6. And why
should they?

Git is amazing, but not that old. It's only been around since 2005 -- one year
after RHEL5 shipped. Because it's fast and reliable, in a short 8 years, Git
has taken 30% of the version-control market away from old, slow systems like
CVS and Subversion.

So, what I often end up doing is downloading the source code for tools I need
and building it on SmarTest workstations. This is a fun game, but I don't
always have time for it. Plus, I suspect that thousands of other test engineers
are doing the same thing, needlessly repeating each other's work.

I want to release my own Open-Source codes, but I need a modern platform so I
can assume that everyone out there is on the same page. What's the point of
writing an hp93k firmware interface in Python 2.7 if no one has Python 2.7 on
their hp93k workstation?

Here comes [Antikc](https://github.com/gitfoxi/antikc) to save the day. Antikc provides:

* Automated bootstrapping for platform tools like Git and Python
* An umbrella project for my Open-Source development

Check out [Antikc on Github](https://github.com/gitfoxi/antikc)!
Let me know what you think in the comments.

