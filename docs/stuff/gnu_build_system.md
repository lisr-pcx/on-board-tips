# GNU Build System

It can be difficult to make a software program portable. Compilers differ from system to system. Certain library functions are missing on some systems. Compiler files (such as C headers) may have different names. Shared libraries may be compiled and installed in different ways. One way to handle platform differences is to write conditionally compiled code but this approach quickly becomes unmanageable.

The GNU Autotools, also known as the GNU Build System, is a suite of build automation tools designed to support building source code and packaging the resulting binaries.  
It supports building a codebase for multiple target systems without customizing or modifying the code. It is available on many Linux distributions and Unix-like environments.

Autotools is part of the GNU toolchain and is widely used in many free software and open source packages. It consists of *Autoconf, Automake, and Libtool*.  
Other related tools are GNU make, GNU gettext, pkg-config, and the GNU Compiler Collection (GCC).

## Use AUTOTOOLS to create a package

Full documentation can be found on official Debian site, anyway...

[Introduction to Debian packaging](https://wiki.debian.org/Packaging/Intro)  
[Be friendly to your packagers](https://wiki.debian.org/SoftwarePackaging)  
[Debian Developers' Reference](https://www.debian.org/doc/manuals/developers-reference/)  
[Debian New Maintainers' Guide](https://www.debian.org/doc/manuals/maint-guide/)  

### Sample project: snake clone

This project is composed by following files:

- **main.cpp**: entry point
- **snake.h**: (header) class in charge to plot the game area and manage the game logic
- **snake.cpp**: (body)

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

```sh
$ g++ *.cpp -o snake -lcurses -Wall
```

### Create a DEBIAN package

Open your project folder, then create the configuration file "configure.ac"

```sh
AC_INIT([snake], [0.1], [user@email.xxx])

AM_INIT_AUTOMAKE

AC_PROG_CPP

AC_CONFIG_FILES([Makefile])

AC_OUTPUT
```

Create the "Makefile.am"

```sh
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

```sh
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
