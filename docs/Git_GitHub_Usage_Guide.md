# Git / GitHub Usage Guide

## 1. Installation
In order to access and upload files to Git repositories without using GitHub, such as pushing a new file created in the PROS Editor, one must install Git.

### How to set up Git for Windows:			(As of 9/6/2018)
1. Go to https://git-scm.com/.

2. Click on the download link, e.g. "Download 2.18.0 for Windows."

3. When the download finishes, run the downloaded file (.exe).

4. Complete each step of the installation executable, **leaving all default settings checked, except for *Install Git Credential Manager.***

5. Once the installation has completed, open up a Command Prompt by Windows searching: *cmd.exe*.

6. In the Command Prompt, verify that Git has installed correctly by typing:
```
git
```

7. If there are no errors from step 6, you now need to "register" your computer with Git. To do so, type:
```
git config --global user.email "you@example.com"
```
replacing *you@example.com* with your GitHub email address and
```
git config --global user.name "Your Name"
```
replacing *Your Name* with your first and last name.

<br>

## 2. Creating a GitHub Account
To create a GitHub account, go to https://github.com/join and follow the prompts.

For more help, visit https://www.wikihow.com/Create-an-Account-on-GitHub.

<br>
<p align="right">
<a href="https://github.com/PYRORobotics/programming-guide/blob/master/docs/GitHub_Style_Guide.md"> <b>Next Page: GitHub Style Guide </b></a>
</p>
<br>
