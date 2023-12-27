# Debugging

Developers spend a considerable amount of time in debugging looking what's going wrong on running code. Learn where to look and how to do it is one of the essential skills of our job.

A **software bug** is a defect in the logic, correctness, or performance of a software system.

+ The program compile but it does not do at runtime what the developer expects *(logic)*
+ The program executes the right path but produces the wrong result *(correctness)*
+ When dependent on worload or external system/architecture *(performance)*
+ When occur in concurrent code and are sporadically observable *(non deterministic)*

Debugging is closely related to testing. *Testing* means we are checking for the presence of a bug, *debugging* is the process of removing an observed fault in software, and both are necessary skills to learn.

## Overview

The following links guide step by step into the argument:

+ [Syntax and Semantics Erros](https://www.learncpp.com/cpp-tutorial/syntax-and-semantic-errors/)
+ [The process](https://www.learncpp.com/cpp-tutorial/the-debugging-process/)
+ [Strategy](https://www.learncpp.com/cpp-tutorial/a-strategy-for-debugging/)
+ [Basic](https://www.learncpp.com/cpp-tutorial/basic-debugging-tactics/)
+ [More](https://www.learncpp.com/cpp-tutorial/more-debugging-tactics/)
+ [Debugger tool: stepping](https://www.learncpp.com/cpp-tutorial/using-an-integrated-debugger-stepping/)
+ [Debugger tool: breakpoints](https://www.learncpp.com/cpp-tutorial/using-an-integrated-debugger-running-and-breakpoints/)
+ [Debugger tool: watch variables](https://www.learncpp.com/cpp-tutorial/using-an-integrated-debugger-watching-variables/)
+ [Debugger tool: call stack](https://www.learncpp.com/cpp-tutorial/using-an-integrated-debugger-the-call-stack/)
+ [Finding issues](https://www.learncpp.com/cpp-tutorial/finding-issues-before-they-become-problems/)

## Strategies

Work experience and practice will improve your skills, but in the meantime apply any kind of tricks usefull for your scenario.

### (1) Scan and Look

Have a look and follow intuition (senior developers get best result compared to junior)

```cpp
#include <iostream>

int main(){
    **int** PI = 3.1415;  // <- BUG logical error/typo
		std::cout << "Value of PI is " << PI << std::endl;
    return 0;
}
```

**TIP** add these flag to the compiler `-Wall` and `-Wextra` in order to catch these kind of errors.

### (2) Printf debugging

Print some values at a particular point of source code to discover the current state of the program

```cpp
#include <iostream>
#include <stdlib.h>

int square(int a){
    return **a**; // <- BUG logical
}

int main(){
		while(1){
				**std::cout << "dbg out 1: " << square(5) << std::endl;**
		    if(square(5)==25){
	          **std::cout << "dbg out 2: " << square(5) << std::endl;**
	          exit(1);
		    }
        **std::cout << "dbg out 3: " << square(5) << std::endl;**
    }
    std::cout << "Exiting program\n";
    return 0;
}
```

**TIP** be aware that on embedded system adding a lot of printf can affect performance and behavior.

### (3) Delta debugging

Don't analyze everything but isolate and check in a kind of way as binary search.

**TIP** verify which functions and code sections are running before analyze code, have a look (and knownledge) of the call stack.

## Links and resources

[Bob Steagall, CppCon 2021, Debugging Techniques](https://youtu.be/M7fV-eQwxrY)

[Mike Shah, CppCon 2022, Debugging in C++](https://youtu.be/YzIBwqWC6EM)

[Debugging with GDB: the GNU Source-Level Debugger](https://sourceware.org/gdb/current/onlinedocs/gdb.html/)
