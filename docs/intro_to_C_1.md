<sub>[Introduction and Installation of PROS](PROS_Guide.md) | [Setting Up the PROS Editor](PROS_Guide_2.md) | **Introduction to Robot Programming: Part 1 - The C Programming Language** | Introduction to Robot Programming: Part 2 - Object Oriented Programming and C++

# Introduction to Robot Programming: Part 1 - The C Programming Language
Written for the 2019-2020 VEX competition season by PYRO Robotics Programming Co-lead Brandon Rice.

## Audience and Scope
This tutorial and its C++ counterpart are meant to help guide someone who has never programmed before on the quest of programming a (VEX) robot. *I put VEX in parentheses as this tutorial will assume that the reader is programming a VEX robot using the V5 system and the PROS Editor. However, I feel it is necessary that I note that many of the topics covered here are general programming (or at least C/C++) concepts that **do transfer to other projects, whether it be programming other robotic systems or even applications such as video games.** *

## Summary
This guide is broken into two parts. Part 1 (this page) covers the basics of the C programming language and how it can be used in PROS to program VEX robots. Part 2 covers what is C++ (object-oriented programming) and how to integrate its functionality.

**Part 1 - The C Programming Language contains the following sections:**
- Preface - *explains how this guide came to be*
- The Programming Workflow
- The PROS Default File System/Structure
- Commenting and Documentation
- Data, Variables, and Operations
- Control Statements
- Outputting Data
- PROS-specific Actions
- User Control (Inputting Data)
- Functions
- Structs

---
---
## Preface
*Feel free to skip this section, unless you would like to read how this guide was created or are interested in PYRO's history.*

<details><summary>Click Here to Show/Hide the Preface</summary>
<p style="background-color:lightgray;">

This guide was brought into existence due to the circumstances regarding our VEX U team following the 2018 VEX World Championships. This was when I joined the team and was excited to contribute my high school VEX and FIRST Robotics programming knowledge and overall passion toward programming. At the time, our team comprised of 6 members. We expected several more students to join our team when the 2018 fall semester started, with university club days/showcases attracting students. We expected and projected to have around a 10 member team. We did not expect to have an initial roster count of 19 members.
<br><br>

*Having a large team can be a blessing, but can also be a curse if proper infrastructure is not in place.*
<br><br>

Ryan, PYRO's other Programming Co-lead, and I had spent the summer of 2018 thinking of programming tutorials and workshops we could use to teach any new members who wanted to be on our programming team but had little-to-no prior programming experience. We attempted to incorporate these workshops throughout the build season. However, these workshops were mostly flawed from the start: 2018 required VEX U teams to use the brand new V5 system and microcontroller, but we were put on a wait list upon purchasing and did not receive the system until December. In addition, V5 uses variants of C++ natively (through PROS), which neither Ryan or I had any experience in. These two facts meant that during our only time before our first competitions (the fall semester) Ryan and I were to try to teach a new programming language to new members that could only be debugged with the new V5 system which we did not have access to.
<br><br>

These unfortunate circumstances led to unfavorable conditions on our programming team during that year. I wont go into details, but our vision of having a programming team in which everyone was on the same page and happily and efficiently working on various subsystems of our robot never materialized.
<br><br>

**As an effort to never again have a dysfunctional programming team, I wrote this guide to help new team members succeed in learning how to program using PROS (C/C++).**

</p>
</details>

---
## The Programming Workflow
include pic created

---
## The PROS Default File System/Structure
PROS is by default very organized in its file structure. Before diving into specific details, one should be familiar with the three main competition modes a VEX robot can be in.

- **Autonomous** - This is the mode in which the robot can only be controlled through preprogrammed instructions (code).
- **Operator Controlled** - Opcontrol for short. This is the mode in which drivers can control the robot through controller input. Also called Teleoperated mode, or **Teleop** for short.
- **Disabled** - This is the mode in which the robot can not be controlled either through code or human interaction. This mode is usually run at all times other than Autonomous and Opcontrol modes.

Two other modes also exist, but exit (i.e. are not supposed to loop) after they complete:

- **Initialize** - This is the mode in which the programmer can run code to set up the robot or the rest of the code. Initialize is only run once upon boot of the V5 microcontroller.
- **Competition Initialize** - This mode is only run if the robot is connected to the Field Management System (FMS) at competition, or is connected to a competition switch. This mode is run after Initialize and before Autonomous, used for initializing competition code such as running an Autonomous selection interface.

All five of these modes are run in the background of the V5 brain and are managed by a task scheduling daemon. You do not need to know what this means, but should know that for this reason, **it is imperative that all loops written in one of the above modes utilize a delay, typically of 10 milliseconds.**

By default, PROS has organized these modes into specific files, and also in specific folders (also called directories). Most programmers will only need to be familiar with two folders:

- **include** - Found under [PROJECT_NAME]/include/, this folder contains header files which lay out declarations of data and data structures, namely called variables. **By default, the files contained in this folder ARE NOT compiled without prior inclusion in a source file.**

- **src** - Pronounced "source", found under [PROJECT_NAME]/src/, this folder contains the main source files (the actual files containing the code that runs). **By default, the files contained in this folder ARE compiled.**

##### *But what is the difference between include code and source code.*

<details><summary>Click Here to Show/Hide</summary>
<p style="background-color:lightgray;">

Generally, the only code actually run is called source code. However, especially in large programs or apps, like much of the Microsoft OS for example, it is good practice to declare variables and data structures in a header file. This allows for better organization and reduces the file's line count. Header files (with file extension ".h" for C and ".hpp" for C++) should be placed in /include/. Then, when a source file needs to access a variable declaration, it just needs to have the following line at the top of the file:
<br><br>
#include "path/to/the/header.h"
<br><br>
Multiple include statements can be made, but they must all be above any real line of code and must be on their own line. Further object declaration versus definition explanation is included below in Data and Variables.

</p>
</details>


The default files that you will be using are as follows:
- /include/main.h
- /src/initilize.cpp
- /src/autonomous.cpp
- /src/opcontrol.cpp

#### /include/main.h
This is the "master" include file that is included by default in initilize.cpp, autonomous.cpp, and opcontrol.cpp. This allows the file it is included in to access the PROS libraries that include important definitions, such as a Motor or a Joystick on a Controller.

#### /src/initilize.cpp
In this file, three of the five competition modes are handled via their same-name functions:

- **initialize()** - will run during the Initialize competition mode.
- **disabled()** - will run during the Disabled competition mode (loops).
- **competition_initialize()** - will run during the Competition Initialize competition mode (loops).

#### /src/autonomous.cpp
- **autonomous()** - will run during the Autonomous competition mode.

#### /src/opcontrol.cpp
- **opcontrol()** - will run during the Opcontrol (Teleop) competition mode (loops).

---

## Commenting and Documentation
**Documentation is perhaps the most important aspect of programming, even more so than having working code.** Without documentation, others will not understand why you wrote what you did, and even you might forget how or why you wrote something. Documentation is done through writing comments next to code.

*Commenting can also be used to temporarily remove lines of code, as the program will not run any actions that are commented out.*

In C and C++, there are three ways of commenting and documenting code.

#### The inline or line comment:
```C
// Do something
```

#### The block comment for multiple lines of code:
```C
/*
These
lines
of
code
are
commented
out!
*/
```

#### The "Javadoc" style documentation comment, usually put directly above custom code definitions that span multiple lines, such as functions:
```C
/**
 * This function, foo, calculates the sum of two integers.
 *
 * Author: Brandon Rice
 */
foo()
{
  1 + 2;
}
```
