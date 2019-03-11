## Data, Variables, and Operations
### **Data**
Data is information typically stored in memory that is a result of computations or computer actions. More specifically to robotics, data is what allows the microcontroller (brain) to remember and store the actions programmed by the programmer. Data can be stored ahead of time, or can also be collected and processed real-time. Data exists in several different **data types:**

#### **bool**
The boolean data type. A bool can store binary data: 0 or 1 (also true or false for logical operations).
#### **int**
The integer data type. An int (by default is 16 bits) which can store integer numbers in the range [−32,767, +32,767] inclusive.
#### **float**
The floating point (decimal) number data type, typically 32 bits in size. Usually we use *double* instead, as it can store double the size of data (32 bits), which might increase the accuracy of the decimal data.
#### **double**
The double (decimal) number data type, typically 64 bits in size.
#### **char**
The character data type. A char can store one character, designated by either its letter, ascii ID, or hex number.

### **Variables**
Variables are user defined pieces of memory that data can be stored in. Variables can be declared for any of the data types, but once declared as one type, the variable can not change to a different type.

#### **Usage and Examples**
Variables can be declared without initially defining its value:
```C
bool myBoolean;
int myInt;
float myFloat;
double myDouble;
char myChar;
```
Then, declared variables can be assigned a value:
```C
myBoolean = true;
myInt = -5;
myFloat = 3.142;
myDouble = 3.141592;
myChar = 'a';
```
At any time in the same scope, these variables can be reassigned a value:
```C
myBoolean = 0;

myChar = 65;
```
Programmers can also declare and define variables in the same line.
```C
int motorSignal = 127;
```

**Now is a good time to explain what the semicolons mean.** The semicolon (;) is used in C and C++ to designate an end to a statement.

**Typically, every line in C, except the exceptions listed below, need to end in a semicolon:**
- Include statements do not end in semicolons:
```C
#include "main.h"
```
- *Some* control statements (or blocks) (explained later) do not end in semicolons:
```C
if(myBoolean == true)
{
  motorSignal = 5;
}
else
{
  motorSignal = -5;
}
while(true)
{
  // Do something
}
```

### **Operations**
Variables (and data in general) can be put through mathematical or logical operations to compute other resulting data.

#### Parentheses
As in mathematics, parentheses can be used with any data type to group operations through standard order of operations.

#### Arithmetic Operations (A.K.A. Math Operations)
Numerical data types and variables can have the following mathematical operations performed on them.

- **+** (Addition)
```C
myInt = 2 + 3;  // myInt will be assigned 5
myInt = myInt + 5;  // myInt will be assigned its value + 5
myInt += 5; // Just as the line above, myInt will be assigned its value + 5
myInt++; // myInt will be assigned a value one greater than its original value (adds one)
```
- **-** (Subtraction)
```C
myInt = 5 - 15;  // myInt will be assigned -10
myInt = myInt - 10;  // myInt will be assigned its value - 10
myInt -= 10; // Just as the line above, myInt will be assigned its value - 10
myInt--; // myInt will be assigned a value one less than its original value (subtracts one)
```
- __*__ (Multiplication)
```C
myInt = 2 * 3;  // myInt will be assigned 6
myInt = myInt * 6;  // myInt will be assigned its value * 6
myInt *= 6; // Just as the line above, myInt will be assigned its value * 6
```
- **/** (Division)
```C
myInt = 10 / 3;  // myInt will be assigned 3
myInt = myInt / 3;  // myInt will be assigned its value / 3
myInt /= 3; // Just as the line above, myInt will be assigned its value / 3

  myDouble = 5 / 15;  // myDouble will be assigned 0.3333333301345 (decimal inaccuracy)
myDouble = myInt / 10;  // myDouble will be assigned its value / 10
myDouble /= 10; // Just as the line above, myDouble will be assigned its value / 10
```
- **%** (Modulus, or the remainder of integer division)
```C
myInt = 10 % 3;  // myInt will be assigned 1 (10/3 = 3 with a remainder of 1)
myInt = myInt % 3;  // myInt will be assigned its value % 3
myInt %= 3; // Just as the line above, myInt will be assigned its value % 3
```

#### Relational (Comparison) Operators
The boolean (binary) data type and variables can be assigned to a result of comparing data through relational operators.

- **==** (Equals - do two values equate?)
```C
  myChar = 'a';
  myBoolean = (myChar == 'a');  // myBoolean will be assigned true
  myBoolean = (myChar == 'A');  // myBoolean will be assigned false
```

- **!=** (Not equals - are two values not equal?)
```C
  myChar = 'A';
  myBoolean = (myChar != 'a');  // myBoolean will be assigned true
  myBoolean = (myChar != 'A');  // myBoolean will be assigned false
```

- **>** (Greater than - is the first value larger than the second?)
```C
  myBoolean = (myInt > 5);
```

- **>=** (Greater than or equal to - is the first value the same as or larger than the second?)
```C
  myBoolean = (myInt >= 5);
```

- **<** (Greater than - is the first value smaller than the second?)
```C
  myBoolean = (myInt < 5);
```

- **<=** (Greater than or equal to - is the first value the same as or smaller than the second?)
```C
  myBoolean = (myInt <= 5);
```

#### Logical Operations
The boolean (binary) data type and variables can have the following logical operations performed on them.

- **&&** (And - both values must be true to evaluate to true)
```C
  bool myBool1 = true;
  bool myBool2 = true;

  myBoolean = myBool1 && myBool2;  // myBoolean will be assigned true

  myBool2 = false;

  myBoolean = myBool1 && myBool2;  // myBoolean will now be assigned false
```

- **||** (Or - one or both values must be true to evaluate to true)
```C
  myBool1 = true;
  myBool2 = true;

  myBoolean = myBool1 || myBool2;  // myBoolean will be assigned true

  myBool2 = false;

  myBoolean = myBool1 || myBool2;  // myBoolean will still be assigned true
```

- **!** (Not - assigns the boolean to its opposite value)
```C
  myBool1 = true;

  myBoolean = !myBool1;  // myBoolean will be assigned false

  myBoolean = !myBoolean;  // myBoolean will now be assigned true
```

#### Combinations of Logical Operations
Operations can be combined to form complex logical relationships:
```C
  myBoolean = (myBool1 && (myBool2 || (myBoolean && myInt > 5) ) );
```
---

## Control Statements

We now know how to store data, but our coding capabilities are still rather raw: we can only program "from the top down," meaning that the program will read our code line-by-line **only once**. But what if we might want our code to make decisions, or loop based on conditions? These features are implemented using control statements. There are three types of control statements: **loops**, **if statements**, and **switch statements.**

### Loops
Looping is useful if you want the same code to run over and over until a condition is met (or forever). There are three types of loops:
#### While Loops
While loops check if the condition is true. If it is, then the code inside of the curly braces ( { } ) will loop until the condition is false. The condition is checked each time the code hits the bottom curly brace.

```C
  myBoolean = true;
  while(myBoolean)
  {
    // Do something
  }
```
#### For Loops
For loops are like while loops, but iterate through a variable until given conditions are false. For loops must specify three "parameters," separated by semicolons: (1) the variable to be iterated, (2) the condition (will loop until false), and (3) how to update the variable.

```C
  for(int i = 0; i < 5; i++)
  {
    // Do something
  }
```
#### Do-while Loops
Do-while loops are like while loops, but must execute the block of code at least once. The condition is only checked after the block has finished executing.

```C
  do
  {

    // This code will be run at least once

  } while(myBoolean);
```

---

## Outputting Data
Comments can give someone feedback on what the programmer intended to write or compute, but what if we want to analyze real time data computations. This can be useful to check for errors, or debug why a program is not running as intended.

To output data in a C-based terminal (like PROS), you can simply write the following:
```C
  printf("This text will be output.");
```

We can include data or variables to be printed by listing them as parameters after the quotation marks ("") and formatting the data in the quotation marks:
```C
  int signal = 127;
  printf("Motor Signal: %d \n", signal);  // \n prints the newline character, writing the next print command to the next line
  double speed = 50;
  printf("Motor Speed: %d RPM", speed);

  // Output: Motor Signal: 127
  //         Motor Speed: 50 RPM
```

*NOTE: PROS is C++ based, and thus also supports std::cout to write to the terminal as explained in Part 2.*
