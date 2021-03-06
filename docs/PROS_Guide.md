<sub>**Introduction and Installation of PROS** | [Setting Up the PROS Editor](PROS_Guide_2.md) | Introduction to C | Introduction to Object Oriented Programming and C++

# PYRO Robotics PROS Guide

## Table of Contents
1. **Introduction and Installation of PROS**
2. [Setting Up the PROS Editor](PROS_Guide_2.md)
2. [Introduction to C](page_comming_soon)
3. [Introduction to Object Oriented Programming and C++](page_comming_soon)

## Introduction

To function, a robot needs a set of instructions of what it is supposed to do. These instructions are written by a **programmer** in a certain **programming language**. The set of instructions, also called **code**, can be typed in any text-based editor. However, to simplify and reduce error, often an **integrated development environment (IDE)** is used. IDEs have plugins that can read, compile, and find syntax and logic errors, among other beneficial uses within your code. Code can take many shapes and forms, but ultimately is a part of a **program**, a collection of code, that is then compiled and deployed to the robot.
 
In 2018, VEX Robotics released the **V5 Control System**. A feature of V5 is the new supported programming languages: C++, RobotC++, Blockly (a graphical language), Python, and JavaScript. Currently, there are several IDEs that can be used to program the V5 Control System: [VEX Coding Studio](https://www.vexrobotics.com/vexedr/products/programming), the [PROS Editor](https://pros.cs.purdue.edu/), and [Robot Mesh Studio](https://www.robotmesh.com/studio). PYRO chooses to use **PROS Editor** to program VEX robots, as it is powerful and clean compared to its alternatives. The latest version, PROS 3, supports programming in **C++** and **C**.

>*PROS (Purdue Robotics Operating System) was created and is maintained by the Purdue ACM SIGBots.*
 
It should be noted that **PROS is an operating system** which includes the VEX libraries and functionality to deploy code to the robot. The IDE that is used by PROS is called the **PROS Editor**, a modified version of **Atom**, a text-based editor. A useful feature in using Atom with PROS is that the programmer can download and use any of the many [custom plugins](https://atom.io/packages) built for Atom, streamlining the process of programming.

**NOTE: Atom is installed automatically by the PROS installer.** You do not need to install Atom separately.
 
>Unless otherwise specified, “PROS” implies the PROS Editor, including both the operating system (libraries) and the IDE (Atom). Example: “How to set up PROS 3 (VEX V5) for Windows” implies also setting up Atom.
 
Prior to the release of the V5 Control System, VEX robots used the Cortex microcontroller brain and were written almost exclusively in the C programming language. Programmers could choose from several IDEs, albeit RobotC was commonly used. The PROS 2 Editor was an alternative IDE, and featured advanced programming capabilities, custom sensor integration, and faster speeds than RobotC.

<br>

## How to set up PROS 3 (VEX V5) for Windows:			(As of 9/4/2018)
1. Go to https://github.com/purduesigbots/pros-cli3/releases.

2. Click on the link corresponding to your operating system to download the installer.

3. When the download finishes, run pros-windows-3.1.2.0-XXbit.exe.

<br>

4. Wait for the installer to finish launching, as shown below. Choose an option for how many users to install PROS for. The default is “Everybody (all users)”, but “Only for me (*username*)” can be chosen to save storage space. When satisfied with your selection, click next.

<br>
<p align="center"> 
<a href="https://github.com/PYRORobotics/programming-guide/blob/master/docs/PROS_Guide.md#how-to-set-up-pros-3-vex-v5-for-windowsas-of-942018"><img src="/images/PROS_GUIDE/image10.png" width="400"></a>
</p>
<br>

5. Choose which features you would like to install, as shown below. “PROS Editor” and “llvm” are necessary. In addition, **to deploy code to the robot, a programming cable driver is needed.** Select the correct programming cable driver according to your computer’s operating system. 32-bit operating systems must use the 32-bit programming cable driver. **If you are unsure of which driver to install, choose the 32-bit driver.**

    If you would like to change where PROS is installed, edit the directory in the “Installation Folder” tab.

<br>
<p align="center"> 
<a href="https://github.com/PYRORobotics/programming-guide/blob/master/docs/PROS_Guide.md#how-to-set-up-pros-3-vex-v5-for-windowsas-of-942018"><img src="/images/PROS_GUIDE/image6.png" width="400"></a>
</p>
<br>

6. Agree to the licensing of PROS and click “Accept and Install” in the bottom-right corner, as shown below.

<br>
<p align="center"> 
<a href="https://github.com/PYRORobotics/programming-guide/blob/master/docs/PROS_Guide.md#how-to-set-up-pros-3-vex-v5-for-windowsas-of-942018"><img src="/images/PROS_GUIDE/image8.png" width="400"></a>
</p>
<br>

7. Wait while the installer installs PROS, as shown below. Do not close the installer in this step, as you will have to run the installer again to install PROS. Depending on your computer, this step may take some time.

<br>
<p align="center"> 
<a href="https://github.com/PYRORobotics/programming-guide/blob/master/docs/PROS_Guide.md#how-to-set-up-pros-3-vex-v5-for-windowsas-of-942018"><img src="/images/PROS_GUIDE/image5.png" width="400"></a>
</p>
<br>

8. Click “Finish” to close the installer. PROS has been successfully installed, as shown below.

<br>

## Legacy: How to set up PROS 2 (VEX Cortex) for Windows:			(As of 7/17/2018)
*It is recommended that you install PROS 3 instead, as it includes support for V5 AND the Cortex.*
1. Go to https://pros.cs.purdue.edu/.
2. Navigate down to the section titled “DOWNLOAD,” as shown below.

<br>
<p align="center"> 
<a href="https://github.com/PYRORobotics/programming-guide/blob/master/docs/PROS_Guide.md#how-to-set-up-pros-2-vex-cortex-for-windowsas-of-7172018"><img src="/images/PROS_GUIDE/image9.png" width="400"></a>
</p>
<br>

3. Click on the “DOWNLOAD” button.
4. Run **pros-win.exe** when the program is done downloading. *If using Google Chrome, the download should appear in the bottom-left corner, as shown below.*

<br>
<p align="center"> 
<a href="https://github.com/PYRORobotics/programming-guide/blob/master/docs/PROS_Guide.md#how-to-set-up-pros-2-vex-cortex-for-windowsas-of-7172018"><img src="/images/PROS_GUIDE/image7.png" width="400"></a>
</p>
<br>

5. Wait for the installer to finish launching, as shown below. Choose an option for how many users to install PROS for. The default is “Everybody (all users)”, but “Only for me (*username*)” can be chosen to save storage space. When satisfied with your selection, click next.

<br>
<p align="center"> 
<a href="https://github.com/PYRORobotics/programming-guide/blob/master/docs/PROS_Guide.md#how-to-set-up-pros-2-vex-cortex-for-windowsas-of-7172018"><img src="/images/PROS_GUIDE/image10.png" width="400"></a>
</p>
<br>

6. Choose which features you would like to install, as shown below. “PROS Editor” and “llvm” are necessary. In addition, **to deploy code to the robot, a programming cable driver is needed.** Select the correct programming cable driver according to your computer’s operating system. 32-bit operating systems must use the 32-bit programming cable driver. **If you are unsure of which driver to install, choose the 32-bit driver.**

    If you would like to change where PROS is installed, edit the directory in the “Installation Folder” tab.

<br>
<p align="center"> 
<a href="https://github.com/PYRORobotics/programming-guide/blob/master/docs/PROS_Guide.md#how-to-set-up-pros-2-vex-cortex-for-windowsas-of-7172018"><img src="/images/PROS_GUIDE/image6.png" width="400"></a>
</p>
<br>

7. Agree to the licensing of PROS and click “Accept and Install” in the bottom-right corner, as shown below.

<br>
<p align="center"> 
<a href="https://github.com/PYRORobotics/programming-guide/blob/master/docs/PROS_Guide.md#how-to-set-up-pros-2-vex-cortex-for-windowsas-of-7172018"><img src="/images/PROS_GUIDE/image8.png" width="400"></a>
</p>
<br>

8. Wait while the installer installs PROS, as shown below. Do not close the installer in this step, as you will have to run the installer again to install PROS. Depending on your computer, this step may take some time.

<br>
<p align="center"> 
<a href="https://github.com/PYRORobotics/programming-guide/blob/master/docs/PROS_Guide.md#how-to-set-up-pros-2-vex-cortex-for-windowsas-of-7172018"><img src="/images/PROS_GUIDE/image5.png" width="400"></a>
</p>
<br>

9. Click “Finish” to close the installer. PROS has been successfully installed, as shown below.

#### Additional Steps
*Creating a desktop shortcut:*

1. Search Windows for **PROS**. This can be done by selecting the Windows icon on the taskbar (or typing the Windows key) and typing **PROS**. Windows should find “PROS Editor x64/x32 Desktop app,” as shown below.

<br>
<p align="center"> 
<a href="https://github.com/PYRORobotics/programming-guide/blob/master/docs/PROS_Guide.md#additional-steps"><img src="/images/PROS_GUIDE/image3.png" width="400"></a>
</p>
<br>

2. Right click on “PROS Editor x64/x32 Desktop app” and select “Open file location,” as shown below.

<br>
<p align="center"> 
<a href="https://github.com/PYRORobotics/programming-guide/blob/master/docs/PROS_Guide.md#additional-steps"><img src="/images/PROS_GUIDE/image4.png" width="400"></a>
</p>
<br>

3. In the Windows Explorer window that popped-up, right click “PROS Editor x32/x64,” hover over “Send to” to bring up options, and click “Desktop (create shortcut).”

<br>
<p align="center"> 
<a href="https://github.com/PYRORobotics/programming-guide/blob/master/docs/PROS_Guide.md#additional-steps"><img src="/images/PROS_GUIDE/image1.png" width="400"></a>
</p>
<br>

## Legacy: PROS 2 (VEX Cortex) for OS-X or Linux:		(As of 7/17/2018)
Follow the official tutorials under **Getting Started / Installing PROS** listed in the official documentation linked below.

<br>

For more details, visit PROS’s official documentation: https://pros.cs.purdue.edu/cortex/getting-started/index.html#installing-pros

<br>

<br>
<p align="right">
<a href="PROS_Guide_2.md"> <b>Next Page: Setting Up the PROS Editor </b></a>
</p>
<br>
