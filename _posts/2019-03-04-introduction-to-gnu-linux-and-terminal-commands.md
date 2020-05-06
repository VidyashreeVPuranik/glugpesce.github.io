---
layout: post
title: Introduction to GNU/Linux and Terminal Commands
categories: event
date: 2019-03-04
author: zphoenix
---
### What is GNU/Linux?

It is an **Operating System** that manages a computer. It is entirely **free**
and large number of developers spread over the world who always contribute for
its development and existence till date. GNU/Linux is the core component and
have different products which are **distributions(distros)** that vary with
appearance and few working mechanism and functions like **Internet/Networking,
or Multimedia and Graphics and etc.** There are hell lot of Free Software which
are not just free but quality applications too. In simple term GNU/Linux is a
collection of many programs, applications, libraries, developer tools, even
games which talks with hardware of a computer.

![GNU/Linux](https://cdn-images-1.medium.com/max/800/0*Z2Jl3oXVUW43JSDh)

There are many distros, choosing the right DISTRIBUTION of GNU/Linux, for
newbies advised Distributions(Distros) are 




The larger picture of a **GNU/Linux** or any **Free Software** are it promotes
users **Freedom to run, copy, distribute, study, change and improve** the
Application. Free software refers to four kinds of freedom,

    The freedom to run the program, for any purpose.

    The freedom to study how the program works, and adapt it to your needs. Access to the source code.

    The freedom to redistribute copies to others.

    The freedom to improve the program, and release your improved to public, so that the whole community benefits. And the source code should be accessed by public.

GNU/Linux is based on **Command Line Interface (CLI)** and nowadays it supports
both **CLI and Graphical User Interface (GUI)**. Most of the functions like to
create or delete a file/folder/directory, execute a program, install or
uninstall, view documents, and etc can be done using a Terminal(also known as
shell). Getting started with Terminal will ease most of your work starting from
using a computer for viewing or managing database to working on a project to
running or deploying a server and many more cool stuffs!!!

### Getting started with TERMINAL

![Terminal](https://cdn-images-1.medium.com/max/600/1*J5bg4fxaOy4atKegwMVM-A.png)

Large portions of GNU/Linux functionality are achieved by using the terminal. A
terminal is a **command-line interpreter** that executes user inputted commands.
**Bash** is a common default shell among many Linux distributions. Learning few
basic commands listed below will make it easy to use any GNU/Linux OS.<br>
**Commands (Terminal is Case-Sensitive)**
1. To Open the Terminal

    $ Ctrl + Alt + T
    $ Ctrl + Shift+ T  (To open terminal in tab fashion)

2. To end a execution

    $ Ctrl + C

3. Clearing the Terminal Screen

    $ clear 
    or 
    $ Ctrl + L

4. To  Auto-complete files or directory names

    TAB (press Tab button)

5. To show all possible files or directory 

    TAB TAB (press Tab button twice

6. For any Help or Information on Commands

    $ man <command name> (To quit a man page use 'q' button)
    or
    $ <command name> --help

7. `ls` stands for *list*.

    $ ls
    $ ls -a  (lists all the files)
    $ ls -l  (lists details like owner, date, type, etc.)
    $ ls - *.pdf  (lists all the files of type pdf, not just pdf it can be other type extensions too)

8. `cd` is Change Directory which allows to traverse through directories and
file paths

    $ cd 
    or 
    $ cd ~  (Changes the current directory to Root Directory)
    $ cd -  (Changes the current directory to previous directory)
    $ cd <dir>  (Changes the current directory to directory <dir>)

9. To display the Current directory

    $ pwd  (Working Directory)

10. To Copy file/Directories

    $ cp <Source> <Destination>  (Copies file from source to destination)
    $ cp file1 file2 file3 ...  dir  (Copies the following files to <dir>)
    $ cp -i  (Ask user confirmation if the target file already exist)
    $ cp -p  (preserves the attributes such as time, mode, ownership of the source file)

11. To Move file

    $ mv <old_name> <new_name>  (Renames a given file or directory)
    $ mv -i  (Ask user confirmation if the new file already exists)
    $ mv -p  (preserves the attributes such as time, mode, ownership of the source file)
    $ mv -f  (Force the move by overwriting the Destination file)

12. To Remove a file(Delete)

    $ rm file1 file2 file3 file4  (Removes the given files)
    $ rm -i  (Ask for user confirmation)
    $ rm -r dir1 dir2 dir3  (Removes the given Directories including contents)
    $ rm -f  (Force remove)

13. Create or Remove Directories

    $ mkdir dir1 dir2 dir3  (Creates directories with given names)
    $ touch <file_name>

    $ rmdir dir1 dir2 dir3  (Removes the given directories only when they are empty)
    $ rm -r <dir>  (Removes the given directories and no need to be empty)
    $ rm -rf <dir>  (Removes the given directories without asking)

14. Displaying Contents of files

    $ cat file1 file2 file3  (Concatenates and outputs the contents of the files)
    $ vi <file_name>  (Edit the given file)

15. To  Search files

    $ grep <pattern> <file>

16. Ordering

    $ sort <file>   (Sorts the lines in the file in Character order and outputs them)
    $ sort -r <file>  (Sorts the lines in reverse order in the file in Character order and outputs them)

17. Echo

    $ echo <option> <String>  (Strings should be represented using double quotes)

18. Find

    $ find <dir> <file_name>

19. To display the current User

    $ whoami

20. Similarly date, calendar, time, and others can be used

    $ date
    $ calendar
    $ time

21. Compressing and Uncompressing

    $ gzip <options><file>
    $ gunzip <options><file>

22. To close terminal 

    Ctrl + Shift + W  (terminal tab)
    Ctrl + Shift + Q  (entire terminal)

### Conclusion

When we have Free Software for very prominent  proprietor  software which gives
the same or better experience, **Why not use it ?** The word free in Free
Software is **free as in Freedom**, the source code is open to all. Few may feel
the source code is open, any one can place a malware and upload, it is
reasonable. But the truth is for every free software there is a** Community of
developers** working on it and developers are assigned roles and any new updates
or upgrades, needs to be reviewed by them(prominent person working in the
community like editors, reviewer, etc). So whenever someone tries to upload a
malware or such, its removed when developers detect them.

So people working on GNU/Linux get the best use and experience Free Software.
Most importantly people interested in **Free Software and its philosophy** need
not contribute only by coding and development but **spreading the knowledge** of
Free Software to our surrounding is also a big contribution for a better **FREE
DIGITAL SOCIETY** that we live in.
