Down below are listed further concepts, articles, projects, topics ... that I can't relate directly to the topics of this site. This page is a kind of a *storage box*, sorry for the mess.

# SMART

This method allows you to write goals that are clear, attainable and meaningful.  
Having clarity in your goal-setting provides the motivation and focus you need to be successful.

+ **S**pecific (simple, sensible, significant)
+ **M**easurable (meaningful, motivating)
+ **A**chievable (agreed, attainable)
+ **R**elevant (reasonable, realistic and resourced, results-based)
+ **T**ime bound (time-based, time limited, time/cost limited, timely, time-sensitive)

[Smart goals](https://asana.com/resources/smart-goals)

# The Google Project Aristotle

The researchers found ([read](https://www.nytimes.com/2016/02/28/magazine/what-google-learned-from-its-quest-to-build-the-perfect-team.html)) that what really mattered was less about who is on the team, and more about how the team worked together. In order of importance:

**Psychological safety** ([video](https://youtu.be/LhoLuui9gX8))  
Team members feel safe to take risks and be vulnerable in front of each other  
*“If I make a mistake on our team, it is not held against me.”*
	
**Dependability**  
Team members get things done on time and meet Google’s high bar for excellence
*“When my teammates say they’ll do something, they follow through with it.”*

**Structure and clarity**
Team members have clear roles, plans and goals
*“Our team has an effective decision-making process.”*

**Meaning**  
Work is personally important to team members
*“The work I do for our team is meaningful to me.”*

**Impact**  
Team members think their work matters and creates change
*“I understand how our team’s work contributes to the organization's goals.”*

The researchers also discovered which variables were not significantly connected with team effectiveness at Google:

+ Collocation of teammates (sitting together in the same office)
+ Consensus-driven decision making
+ Extroversion of team members
+ Individual performance of team members
+ Workload size
+ Seniority
+ Team size
+ Tenure

It’s important to note though that while these variables did not significantly impact team effectiveness measurements at Google, that doesn’t mean they’re not important elsewhere.

> The fundamental thing that distinguish good teams from disfunctional ones is how team mates treat one another.  
> *Sandi Metz*

# Conferences on work-Life balance and career tips

**[Love Your Work - Simon Sinek](https://youtu.be/jDIZS4IQlQk)**  
Simon Sinek speaks on how to be fulfilled by your job and how companies can better support and inspire the people who work for them.

**[How to Become Accomplished - Chad Fowler](https://youtu.be/hsIcFf9pnCo)**  
We work in a time and culture of incredibly hard work. When someone asks how you're doing, how often do you use the word "busy" in the answer? But, what are we busy doing?  
As a professiional musician, I learned that the most successful musicians are rarely the best musicians. This holds true in the technology business world. It's also true that the busiest, hardest working among us aren't necessarily the most accomplished.  
So, what is accomplishment, and how do we get it?

**[An Engineer's Guide To Burnout And How To Hack It - Tim Duckett](https://youtu.be/jfQ5M6wXi2w)**  
The tech industry is notorious for its masochistic approach to deadlines, workloads and hours spent toiling at the code face. The projects might ship, but what's the long-term cost to our physical and mental health?  
It doesn't have to be this way - in this session, Tim will draw from both practical experience of (just about) surviving death march projects and Proper Psychological Science to show how burnout happens, what causes it, and what we can do to survive.

# Conferences about programming

**[Legacy - Chad Fowler](https://youtu.be/YruzQgWdv48)**  
As software developers, we learn to abhor maintaining other people's old software. It's old, funky and brittle. In fact, we spend much of our work lives trying to kill it or at the very least marginalize its use, so we can limit our exposure to it. We pity people who have to do it [..]

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

# Lead and relationship

[Radical candor](https://youtu.be/MIh_992Nfes)  
[Most Leaders Don't Even Know the Game They're In](https://youtu.be/RyTQ5-SQYTo)  