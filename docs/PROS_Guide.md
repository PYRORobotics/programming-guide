# PYRO Robotics PROS Guide

## Introduction

To function, a robot needs a set of instructions of what it is supposed to do. These instructions are written by a **programmer** in a certain **programming language**. The set of instructions, also called **code**, can be typed in any text-based editor. However, to simplify and reduce error, often an **integrated development environment (IDE)** is used. IDEs have plugins that can read, compile, and find syntax and logic errors, among other beneficial uses within your code. Code can take many shapes and forms, but ultimately is a part of a **program**, a collection of code, that is then compiled and deployed to the robot.
 
In 2018, VEX Robotics released the **V5 Control System**. A feature of V5 is the new supported programming languages: C++, RobotC++, Blockly (a graphical language), Python, and JavaScript. Currently, there are several IDEs that can be used to program the V5 Control System: [VEX Coding Studio](https://www.vexrobotics.com/vexedr/v5#coding), the [PROS Editor](https://pros.cs.purdue.edu/), and [Robot Mesh Studio](https://www.robotmesh.com/studio). PYRO chooses to use **PROS Editor** to program VEX robots, as it is powerful and clean compared to its alternatives. The latest version, PROS 3, supports programming in **C++** and **C**.

>*PROS (Purdue Robotics Operating System) was created and is maintained by the Purdue ACM SIGBots.*
 
It should be noted that **PROS is an operating system** which includes the VEX libraries and functionality to deploy code to the robot. The IDE that is used by PROS is called the **PROS Editor**, a modified version of **Atom**, a text-based editor. A useful feature in using Atom with PROS is that the programmer can download and use any of the many custom plugins built for Atom, streamlining the process of programming.

**NOTE: Atom is installed automatically by the PROS installer.** You do not need to install Atom separately.
 
>Unless otherwise specified, “PROS” implies the PROS Editor, including both the operating system (libraries) and the IDE (Atom). Example: “How to set up PROS 3 (VEX V5) for Windows” implies also setting up Atom.
 
Prior to the release of the V5 Control System, VEX robots used the Cortex microcontroller brain and were written almost exclusively in the C programming language. Programmers could choose from several IDEs, albeit RobotC was commonly used. The PROS 2 Editor was an alternative IDE, and featured advanced programming capabilities, custom sensor integration, and faster speeds than RobotC.

<br>

## How to set up PROS 3 (VEX V5) for Windows:
Note: PROS 3 will not be publicly released until August 2018.

<br>

## How to set up PROS 2 (VEX Cortex) for Windows:			(As of 7/17/2018)
