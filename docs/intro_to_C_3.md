## PROS-specific Actions

This section aims to familiarize you with many of the major functions used to program VEX Robots with PROS. What functions are is discussed later, but for now, think of functions as a way to tell your robot to do a specific pre-programmed action.

*NOTE: This section is rather obsolete with PROS transitioning to an almost entirely C++ based format/syntax. It is recommended to skip to Part 2's PROS-specific Actions section.*



## User Control (Inputting Data)
Typically, a section titled *Inputting Data* in a software programming tutorial goes into detail of how to record keyboard input. However, due to this tutorial being specific to VEX Robotics and PROS, in which keyboards (computers) are not primarily used to control the robots, **this section will instead feature how data is collected from a VEX joystick controller.**

*NOTE: This section is rather obsolete with PROS transitioning to an almost entirely C++ based format. It is recommended to skip to Part 2's User Control (Inputting Data) section.*

---
---

**Congratulations!** At this point in this tutorial, you have all of the "tools in your toolbox" required to write robot programs. I suggest if you haven't already, create a PROS project and start playing around, writing code, and having fun exploring programming and the PROS ecosystem. **With that being said,** it is recommended to continue reading this tutorial as it covers many more beneficial features that can improve efficiency, save time, and improve your style and programming habits.

First up, we will learn about functions, a way to improve your code's readability and efficiency.
## Functions
Suppose you want to want to have your robot perform a list of actions repetitively, like turning on a motor for 2 seconds and then turning off the motor for 2 seconds. You want to repeat this process 10 times. Let's do the math: programming the above code would normally require 40 lines of code. That is, in the simplest fashion, 10 motor "on" commands, 10 "wait for 2 seconds" commands, 10 motor "off" commands, and another 10 "wait for 2 seconds" commands. **Programming these 40 lines of code is very time consuming, inefficient, and the final product can be difficult to determine errors due to the lack of readability.**

```C
// 1st time
motor = 127;  // 1
delay(2000);  // 2
motor = 0;    // 3
delay(2000);  // 4
.
.
.
// 10th time
motor = 127;  // 37
delay(2000);  // 38
motor = 0;    // 39
delay(2000);  // 40
```

**A much better way to writing this sequence of actions is to use a function to organize the code that is repeated, and then call the function 10 times.**

A function is a block of code that is optionally given parameters (data passed into the function from outside the function) by the user, perform actions, and optionally returns data. Functions are defined in the following manner:

```C
returned_data_type functionName( data_type parameter1, data_type parameter2, ... )
{
  returned_data_type dataToReturn;
  // Do something
  return dataToReturn;
}
```

Here is an example:

```C
int calculateSum( int num1, int num2 )
{
  int sum;
  sum = num1 + num2;
  return sum;
}
```

This calculateSum() can be further simplified based on user preference:

```C
int calculateSum( int num1, int num2 )
{
  return num1 + num2;
}
```

One data type that is vastly used in functions that we did not cover yet is the absence of a data type. This is referred to as **void**. When a function is declared as void, it does not need a return statement as it cannot return data.

```C
void updatePosition()
{
  // Do stuff
}
```
Notice how updatePosition() doesn't declare any parameters, as they are optional.

Getting back to our motor example, we can write a function to hold the base code that is repeated each time. We can then call the function 10 times over to achieve the desired result.
```C
void myMotorFunction(Motor motor)
{
  motor = 127;
  delay(2000);
  motor = 0;
  delay(2000);
}

.
.
.

// In another function:
Motor motor1(1);
myMotorFunction(motor1); // 1st time
myMotorFunction(motor1); // 2nd time
myMotorFunction(motor1); // 3rd time
myMotorFunction(motor1); // 4th time
myMotorFunction(motor1); // 5th time
myMotorFunction(motor1); // 6th time
myMotorFunction(motor1); // 7th time
myMotorFunction(motor1); // 8th time
myMotorFunction(motor1); // 9th time
myMotorFunction(motor1); // 10th time
```

We can further simplify this code by placing the myMotorFunction() calls in a for loop:

```C
void myMotorFunction(Motor motor)
{
  motor = 127;
  delay(2000);
  motor = 0;
  delay(2000);
}

.
.
.

Motor motor1(1);
for(int i = 0; i < 10; i++)
{
  myMotorFunction(motor1);
}
```

What originally took 40 lines of code was compressed into 12 lines of code, *a 70% reduction!*
