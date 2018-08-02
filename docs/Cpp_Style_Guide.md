# C++ Style Guide

PYRO strives to incorperate good style when writing C++ files, as found in robot code (created since 2018). **Google** provides an [in-depth guide](https://google.github.io/styleguide/cppguide.html) to follow in C++ naming convention and type usage. Important C++ conventions (some not described in Google's guide) are described below:

**1. Comments**

Comments should exist in reference to nearly all lines of code, especially for custom created definitions and usages.
* Single line comments should be used after statements.
* Multiple line comments should be used at the top of each file, before function/class definitions, and to comment out blocks of code.

*Example:*
```C++
/*
 * Title: Foobar.cpp
 * 
 * Summary: Contains counter function
 *
 * ©2018
 */
 
#include <iostream>
using namespace std;

 
/*
 * The function counter is used to print from 0 to num.
 *
 * Peram: int num - the number to count to
 *
 * Returns: void
 */
void counter( int num )
{
  for( int i = 0; i <= num; i++ ) // From 0 to num times...
  {
    cout << i << endl;  // Print the current itteration number
  }
}


int main ()
{
 counter(4);  // 4 is the magic number

 return 0;
}
```

**2. Functions**

PYRO writes a function's opening brace (curly brackets) on its own line, the line following the function declaration.

*Example:*
```C++
int foobar()
{
  // Do something
}
```

**3. Classes**

C++ is an object-oriented language, and such, objects are expected to be extensively used.

Google recommends:
> Use a struct only for passive objects that carry data; everything else is a class.

NOTE: Remember to always define the scope of member variables and functions. Member variables above the first declaration (or no declaration) of scope are **private**, but it is still best to define all public, private, and protected member variables.
