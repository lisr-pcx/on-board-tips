# Linux OS

Linux is one of the most versatile operative systems available today. There are different *flavors* but most of the concepts are applicable on any distribution (following notes are based on Debian 11.6).

!!! tip
    Makeyou confortable to use linux shell.  
    Most of the time the target system does not run a Desktop GUI and you will connect via SSH.

## Quick overview on OS

What's an OS.  
Differente layers and components.  
Linux distributions.

## Basic commands

Work on files, folder, ...

```bash
$ pwd
$ ls -la
$ mkdir <DIR PATH>
$ rmdir <DIR PATH>
$ rm -rf <DIR PATH>
$ mv <FILE OR DIR PATH> <NEW FILE OR DIR PATH> 
$ cp <FILES OR DIR PATH> <NEW FILES OR DIR PATH> 

$ touch <FILE PATH>
$ vi <FILE PATH>
$ nano <FILE PATH>
$ cat <FILE PATH>
```

TAR is a tool to archive files, it creates a single file out of multiple ones (*archiving* .tar file) and if requested it can also reduce the final size (*compression* .tar.gz using GZIP). The final file is often called "tarball".

```bash
$ tar cvf <TARBALL NAME>.tar <SOURCE DIRNAME>
$ tar cvzf <TARBALL NAME>.tar.gz <SOURCE DIRNAME>
$ tar tvf <TARBALL FILE>
$ tar rvf <TARBALL NAME>.tar <FILES OR DIRNAME TO APPEND>
$ tar xvf <TARBALL FILE>
$ tar xvf <TARBALL FILE> -C <DESTINATION DIRNAME>
```

Install, update, remove software (packages).

```bash
$ apt edit-sources
$ apt update
$ apt list --installed
$ apt show <PACKAGE NAME>
$ apt search <PACKAGE NAME>
$ apt install <PACKAGE NAME>
$ apt remove <PACKAGE NAME>
```

!!! note
    Some of the commands above shall be run as admin.  
    Add `su` or `sudo` before the desired command to run it with priviledges.

!!! tip
    All the commands have a specific manual page with usage and flags description.
    Check syntax and options to get desired result.    
    `$ man <COMMAND>`

!!! tip
    UNIX derived systems work with the pipeline mechanism, a really cool way to process an output through mutiple stages.  
    Example: if your command return a bigger list of items, you can filter them in order to get only the relevant ones, and then make it scrollable on the screen just by adding:
    `$ <COMMAND> | grep <FILTER> | less`

### Editing files

Two editors are always available on Linux systems: `nano` (simple and straightforward) or `vi` (less intuitive but powerful).  
I suggest to learn basic few operations on both editors:

* open, save, save as, close
* search a word
* copy and paste text

## Use AUTOTOOLS to create a package

### Sample project: snake clone

This project is composed by following files:

* **main.cpp**: entry point
* **snake.h**: (header) class in charge to plot the game area and manage the game logic
* **snake.cpp**: (body)

The game uses "curses" library for plotting the graphical elements via text console.

```cpp
// File: main.cpp
#include <iostream>
#include <curses.h>
#include <unistd.h>
#include "snake.h"

int main()
{    
    // code
}
```

```cpp
// File: snake.h
#ifndef SNAKE_H
#define SNAKE_H

// define

#include <iostream>
#include <stdlib.h>
#include <time.h>
#include <curses.h>

class Snake
{
public:
  // code
}
```

```cpp
// File: snake.cpp
#include "snake.h"

Snake::Snake()
{
	// code
}

int Snake::Run()
{
  // code
}
```

The program can be compiled and run using:

```bash
$ g++ *.cpp -o snake -lcurses -Wall
```

### Create the package

Open your project folder, then create the configuration file "configure.ac"

```bash
AC_INIT([snake], [0.1], [lisr-pcx@mail.com])

AM_INIT_AUTOMAKE

AC_PROG_CPP

AC_CONFIG_FILES([Makefile])

AC_OUTPUT
```

Create the "Makefile.am"

```bash
bin_PROGRAMS = snakegame
snakegame_SOURCES = snake.cpp

clean-local:
        @rm config.status configure config.log
        @rm Makefile
        @rm -r autom4te.cache/
        @rm aclocal.m4
        @rm compile install-sh missing Makefile.in
```

Finally run commands:

```bash
$ aclocal
$ autoheader
$ autoconf
$ automake
$ automake --add-missing
$ ./configure
$ make
$ make dist
```

At this stage make sure your tarball works fine, copy into your testing OS, extract and run again `./configure` and `make`.

## Create a DEBIAN package

Full documentation can be found on official Debian site, anyway...

[Introduction to Debian packaging](https://wiki.debian.org/Packaging/Intro)

[Be friendly to your packagers](https://wiki.debian.org/SoftwarePackaging)

[Debian Developers' Reference](https://www.debian.org/doc/manuals/developers-reference/)

[Debian New Maintainers' Guide](https://www.debian.org/doc/manuals/maint-guide/)




```bash


```

!!! tip
    Text tip.   
    Second line.  
    Last line.

## Links

[Text](https://google.com)  
