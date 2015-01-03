[![Build Status](https://travis-ci.org/leepike/Copilot.svg?branch=master)](https://travis-ci.org/leepike/Copilot)

Copilot: a stream DSL
====================================
Copilot is a stream (i.e., infinite lists) domain-specific language (DSL) in
Haskell that compiles into embedded C.  Copilot is similar in spirit to
languages like Lustre.  Copilot contains an interpreter, multiple back-end
compilers, and other verification tools.

Resources
=========
Copilot is comprised of a number of sub-projects which are automatically
installed when you install Copilot from Hackage, as described below.  (These are
tracked as Git submodules in Copilot.)

* [copilot-language](http://hackage.haskell.org/package/copilot-language) The
  front-end of Copilot defining the user language.

* [copilot-libraries](http://hackage.haskell.org/package/copilot-libraries)
  User-supplied libraries for Copilot, including linear-temporal logic,
  fault-tolerant voting, regular expressions, etc.

* [copilot-core](http://hackage.haskell.org/package/copilot-core) The core
  language, which efficiently represents Copilot expressions.  The core is only
  of interest to implementers wishing to add a new back-end to Copilot.

* [copilot-cbmc](http://hackage.haskell.org/package/copilot-cbmc) A tool to
  generate a driver using CBMC, a third-party tool (see Dependencies below) that
  proves that the code generated by different C back-ends is equivalent.
  Currently, this includes the C99 back-end and the SBV back-end.

* [copilot-c99](http://hackage.haskell.org/package/copilot-c99) A back-end that
  translates to [Atom](http://hackage.haskell.org/package/atom) to
  generate hard real-time C code.

Optionally, you may which also to install

* [copilot-sbv](http://hackage.haskell.org/package/copilot-sbv) Another back-end
  that translates to [SBV](http://hackage.haskell.org/package/sbv), using its
  code generator to generate hard real-time C code as well.  The ad

* [copilot-discussion](https://github.com/leepike/copilot-discussion)
  Contains a tutorial, todos, and other items regarding the Copilot system.

**Sources** for each package are available on Github as well.  Just go to
[Github](github.com) and search for the package of interest.  Feel free to fork!

Comments, bug reports, and patches are always welcome.  Send them to leepike @
gmail.com

Examples
=========
Please see the files under the Examples directory for a number of examples
showing the syntax, use of libraries, and use of the interpreter and back-ends.
The examples is the best way to start.

Installation
============

* From Hackage:

  The Copilot library is cabalized. Assuming you have cabal and the GHC compiler
  installed (the [Haskell Platform](http://hackage.haskell.org/platform/) is the
  easiest way to obtain these), it should merely be a matter of running

           cabal install copilot

  with an Internet connection.  Please see the INSTALL file for installation
  details.

* From GitHub:

           git clone https://github.com/leepike/Copilot.git
           git submodule update --init
           make test

Once the installation is done, you can run the executable `XXX` which will
execute the regression test suite for sbv on your machine.

Note there is a TravisCI build (linked to at the top of this README) if you have
trouble building/installing.

Dependencies
=============
copilot-cbmc depends on the C model-checker, CBMC.
[CBMC](http://www.cprover.org/cbmc/) is a bounded model-checker for C code.  We
use CBMC to prove that two back-ends generating C generate semantically
equivalent C, to help detect bugs in C back-ends.

Copyright, License
==================
Copilot is distributed with the BSD3 license. The license file contains the
[BSD3](http://en.wikipedia.org/wiki/BSD_licenses) verbiage.

Thanks
======
Copilot was developed, in part, with support from NASA's Aviation Safety
Program, Contract #NNL08AD13T.  Copilot was developed jointly by Galois,
Inc. and the National Institute of Aerospace.

The following people have contributed to Copilot: Lee Pike, Nis Wegmann,
Sebastian Niller, Robin Morisset, Alwyn Goodloe, and Levent Erkok.

