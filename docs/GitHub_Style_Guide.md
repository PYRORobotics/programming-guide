# Git / GitHub Style Guide

## File Naming Conventions

#### Folders
Folders in a Git repository should use **Mixed_Case_With_Underscores** format.

*Example:* The folder **Robot_1** in PYRORobotics/vexu-2018-2019/Robot_1

---
#### General Files
Standard files should use the recommendations found in [ASU's File Naming and Versioning guide](https://researchadmin.asu.edu/dmp/file-naming-and-versioning).

---
#### Repositories
As per [this article](https://github.com/bcgov/BC-Policy-Framework-For-GitHub/blob/master/BC-Gov-Org-HowTo/Naming-Repos.md#follow-conventions), PYRO names repositories as descriptive (but brief) and uses delimiter-separated words, as in **lisp-case** / **spinal-case** / **dash-case**.

*Example:* PYRORobotics/**style-guide**

If PYRO expands to multiple teams, repositories should be named such that an identifier (i.e. name or number) is appended to the existing style.

*Example:* **PYRORobotics/vexu-20xx-20xx-team-1**

---
#### This Style Guide
For PYRO Robotics Programming Style Guide entries, files should be written in Markdown format (**.md**) and named in **Mixed_Case_With_Underscores**. Visit [this article](https://guides.github.com/features/mastering-markdown/) to learn more about the Markdown format. Also, here is a [visual Markdown cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).

*Example:* **GitHub_Style_Guide.md**

<br>

## Organization (File Path)

#### Repositories
All PYRO VEXU robot code is located in specific repositories labeled by year, as in: **PYRORobotics/vexu-20xx-20xx**. Should multiple robots need be built in one year, each robot should have its own folder in the main directory of the year's repository.

*Example:* **PYRORobotics/vexu-2018-2019/Robot_1**

---
#### This Style Guide
All PYRO Robotics Programming Style Guide entries are located under **/style-guide/docs/**.

<br>

## Commits
Each commit contains two text fields: a summary and a description.

[This article](https://github.com/agis/git-style-guide#messages) describes how to write a sufficient commit, as detailed below:

>The summary line (ie. the first line of the message) should be descriptive yet succinct. Ideally, it should be no longer than 50 characters. It should be capitalized and written in imperative present tense. It should not end with a period since it is effectively the commit title:
```
#good - imperative present tense, capitalized, fewer than 50 characters
Mark huge records as obsolete when clearing hinting faults

#bad
fixed ActiveModel::Errors deprecation messages failing when AR was used outside of Rails.
```
>After that should come a blank line followed by a more thorough description. It should be wrapped to 72 characters and explain why the change is needed, how it addresses the issue and what side-effects it might have.

>It should also provide any pointers to related resources (eg. link to the corresponding issue in a bug tracker):
Short (50 chars or fewer) summary of changes
```
More detailed explanatory text, if necessary. Wrap it to
72 characters. In some contexts, the first
line is treated as the subject of an email and the rest of
the text as the body.  The blank line separating the
summary from the body is critical (unless you omit the body
entirely); tools like rebase can get confused if you run
the two together.

Further paragraphs come after blank lines.

- Bullet points are okay, too

- Use a hyphen or an asterisk for the bullet,
  followed by a single space, with blank lines in
  between

The pointers to your related resources can serve as a footer
for your commit message. Here is an example that is referencing
issues in a bug tracker:

Resolves: #56, #78
See also: #12, #34

Source http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html
```
