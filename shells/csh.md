---
tags:
    - shell
    - csh
    - echo
    - script
    - linux
categories:
    - shells
---

# CSH

The ***C shell*** (***csh*** or the improved version, ***tcsh***) is a Unix shell created by Bill Joy while he was a graduate student at University of California, Berkeley in the late 1970s. It has been widely distributed, beginning with the 2BSD release of the Berkeley Software Distribution (BSD) which Joy first distributed in 1978. Other early contributors to the ideas or the code were Michael Ubell, Eric Allman, Mike O'Brien and Jim Kulp.

The C shell is a command processor which is typically run in a text window, allowing the user to type and execute commands. The C shell can also read commands from a file, called a script. Like all Unix shells, it supports filename wildcarding, piping, here documents, command substitution, variables and control structures for condition-testing and iteration. What differentiated the C shell from others, especially in the 1980s, were its interactive features and overall style. Its new features made it easier and faster to use. The overall style of the language looked more like C and was seen as more readable.

On many systems, such as macOS and Red Hat Linux, *csh* is actually *tcsh*, an improved version of *csh*. Often one of the two files is either a hard link or a symbolic link to the other, so that either name refers to the same improved version of the C shell. The original *csh* source code and binary are part of NetBSD.

On Debian and some derivatives (including Ubuntu), there are two different packages: *csh* and *tcsh*. The former is based on the original BSD version of *csh* and the latter is the improved *tcsh*.

*tcsh* added filename and command completion and command line editing concepts borrowed from the Tenex system, which is the source of the "t". Because it only added functionality and did not change what already existed, *tcsh* remained backward compatible with the original C shell. Though it started as a side branch from the original source tree Joy had created, *tcsh* is now the main branch for ongoing development. *tcsh* is very stable but new releases continue to appear roughly once a year, consisting mostly of minor bug fixes.

## Cheat sheet

![CSH cheat sheet](assets/csh.pdf)
