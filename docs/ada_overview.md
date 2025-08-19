# ADA language

Ada is a state-of-the art programming language that development teams worldwide are using for critical software: from microkernels and small-footprint, real-time embedded systems to large-scale enterprise applications, and everything in between.

Ada is a structured, statically typed, imperative, and object-oriented high-level programming language, inspired by Pascal and other languages. It has built-in language support for design by contract (DbC), extremely strong typing, explicit concurrency, tasks, synchronous message passing, protected objects, and non-determinism. It improves code safety and maintainability by using the compiler to find errors in favor of runtime errors.

## Features

- Strong typing
- Modular programming mechanisms (packages)
- Run-time checking
- Parallel processing (tasks, synchronous message passing, protected objects, and nondeterministic select statements)
- Exception handling
- Generics
- Object-oriented programming (from Ada95)

The **Ravenscar profile** is a subset of the Ada tasking features designed for safety-critical hard real-time computing. It was defined by a separate technical report in Ada 95 and it is now part of the Ada 2012 Standard.

The **SPARK** language consists of a well-defined subset of the Ada language that uses contracts to describe the specification of components in a form that is suitable for both static and dynamic verification. It is intended for developing high integrity software used in systems where predictable and highly reliable operation is essential, facilitating development of applications that demand safety, security, or business integrity.

## Get started

I highly recommend to start from the site [LEARN.ADACORE.COM](https://learn.adacore.com).

AdaCore (founded in 1994) is the leading provider of commercial and open-source software solutions for Ada language. It also provide an IDE available [here](https://www.adacore.com/download) (Community version).

For a quick overview of the IDE: GNAT Programming Studio (also names GPS), please refer to [GPS tutorial](https://docs.adacore.com/live/wave/gps/html/gps_tutorial/intro.html).

For the **newbie**:

- Start from [Introduction to Ada](https://learn.adacore.com/courses/intro-to-ada/index.html) and follow the proposed index, and do exercises available on [Introduction to Ada: Laboratories](https://learn.adacore.com/labs/intro-to-ada/index.html)

For **seasoned programmers** who have *strong* background on C, C++ ora Java and nned to ramp-up quickly, then skip the basics for now, and just compare the two languages:

- [Ada for the embedded C developer](https://learn.adacore.com/courses/Ada_For_The_Embedded_C_Developer/index.html)  
- [Ada for C++/Java developer](https://learn.adacore.com/courses/Ada_For_The_CPP_Java_Developer/index.html)  

## Learn by building small projects

TODO

## Focus on ..

- TODO Interface with C language
- TODO GUI frameworks

## References

[AdaCore](https://www.adacore.com/products/languages)  
[AdaCore about Ada](https://www.adacore.com/about-ada)  
[AdaCore GNAT Studio](https://www.adacore.com/gnatpro/toolsuite/gnatstudio)  

## Tools

[Compiler Explorer](https://godbolt.org/): interactive online tool that lets you type code in one window and see the results of its compilation in another window.
