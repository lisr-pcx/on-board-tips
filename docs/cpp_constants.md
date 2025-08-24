# Constants

Basically there are two ways (*keywords*) to manage it:

+ **const** it applies to variables and objects and prevents them from being modified in the code. It allows you to communicate to both compilers and other programmers that a value should remain invariant. [Link](https://en.cppreference.com/w/cpp/language/cv)
+ **constexpr** tell to the compiler to evaluate the variable or the expression at compile time. It's typically used to assign constant variables, array sizes, and store them into read-only memory. [Link](https://en.cppreference.com/w/cpp/language/constexpr)

## const

Google C++ guidelines: [link](https://google.github.io/styleguide/cppguide.html#Use_of_const)  
Abseil Tip of the Week about const: [link](https://abseil.io/tips/109)

```cpp
int main()
{
  int arr[] = {1, 2, 3, 4};
  int val = 25;

  // Tip(!)
  // Read from right to left (following the rule that
  // const always follows the object it's describing...)

  // pointers

  int * a = arr;
  a++;        // valid
  *a = 20;    // valid

  int const * b = arr;
  b++;        // valid
  *b = 20;    // ERROR

  int * const c = arr;
  c++;        // ERROR
  *c = 20;    // valid

  int const * const d = arr;
  d++;        // ERROR
  *d = 20;    // ERROR

  int * p1 = &val;
  int const * p2 = p1;  // valid
  int * p3 = p2;        // ERROR const-ness can not be removed
  int * const p4 = p1;  // valid

  // references

  int & r1 = val;
  int const & r2 = r1;  // valid
  int & r3 = r2;        // ERROR const-ness can not be removed
  int & const r4 = r1   // ERROR const-ness can not be added to ref.
  
  return 0;
}
```

## constexpr, constinit, consteval

Google C++ guidelines: [link](https://google.github.io/styleguide/cppguide.html#Use_of_constexpr)

Some variables can be declared constexpr to indicate the variables are true constants, fixed at compilation/link time. Some functions and constructors can be declared constexpr which enables them to be used in defining a constexpr variable. Functions can be declared consteval to restrict their use to compile time.

Use **constexpr** to specify true constants (fixed at compilation time). Also functions can be declared as **constexpr** and if it's not possible to evaluate at compile time they will managed as normal functions at run-time.  
Use **constinit** to ensure constant initialization for non-constant variables.  
Use **consteval** only for compile time.

## Video / Conferences

[CppCon 2015: Richard Powell “The Importance of Being const"](https://youtu.be/Y1KOuFYtTF4)  
[CppCon 2021: Jason Turner "Your New Mental Model of constexpr"](https://youtu.be/MdrfPSUtMVM)
[Back to Basics: const and constexpr - Rainer Grimm - CppCon 2021](https://youtu.be/tA6LbPyYdco)

## Links

[Stackoverflow Post](https://stackoverflow.com/questions/14116003/whats-the-difference-between-constexpr-and-const)  
[Medium "Understanding the power of constexpr"](https://medium.com/@elysiumceleste/understanding-the-power-of-constexpr-in-c-33aca6f9880)  