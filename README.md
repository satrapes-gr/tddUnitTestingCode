tddec-code
==========

Book code for Test-Driven Development for Embedded C

This directory structure is not exactly the same as the structure
of the code in Test-Driven Development for Embedded C.  I flattened
the structure so that there are no projects inside of projects.

-----------------------------------------
Instructions for building the book's code
-----------------------------------------

1) Download and build CppUTest from cpputest.org. Put CppUTest somewhere like
    ~/tools/cpputest

2) Define an environment variable to point to where you put CppUTest, like

    % export CPPUTEST_HOME=~/tools/cpputest

    Under windows you can use the control panel to set the environment variable.

3) Unzip the code into some directory /path/to/code/root. Make sure the path contains no spaces.
You should end up with this:
    /path/to/code/root/code
    /path/to/code/root/code-t0
    /path/to/code/root/code-t1
    /path/to/code/root/code-t2
    /path/to/code/root/code-t3
    /path/to/code/root/SandBox

4) Build the examples

-------------
For gcc users
-------------
Build all examples
    % cd /path/to/code/root
    % make


Clean all
    % cd /path/to/code/root
    % make

To make a specific project from the command line (code-t0 for example)

    cd /path/to/code/root/code-t0
    make

-----------------
For eclipse users
-----------------
    Here's how to load the projects into eclipse:
    
    1) Install eclipse/cdt
    2) Select the /path/to/code/root directory as the workspace    
    3) Import each project using:
        File/Import.../General/Existing Project into Workspace
    4) Browse, but do not change the directory. Accept the directory
    5) The projects will be list, accept them.
    6) Enjoy

-----------------------
For visual studio users
-----------------------
    The ".dsp" and ".dsw" files provided for Visual Studio version 6 are likely out of date.
    I may work on this.  If you want to make Visual Studio support files for some or all of
    the projects, please fork the repo make the changes and send me a pull request.

-------------
For everybody
-------------
When you look at the downloaded code, you will see some distracting comments throughout the code
that look like this:

    /* START: codeIncludeTag */
    ...
    ... code ...
    ...
    /* END: codeIncludeTag */

These allow the code to be kept separate from the book text. This keeps the examples compilable
and avoids book/code conflicts.  The "START: codeIncludeTag" and "END: codeIncludeTag"
tags identify code that is pulled into the book during the automated book build process. 
Try to ignore them.

You will also notice some code that has been turned off using conditional compilation. 
It looks like this:

    #if 0 /* START: IsOnTake1 */
    BOOL LedDriver_IsOn(int ledNumber)
    {
        return TRUE;
    }
    #endif /* END: IsOnTake1 */

Code in the #if 0 block is a snapshot of code that has since evolved. It may or may 
not have code include tags.  In this book, the code is always evolving.  I've left 
the latest version at the top of the file and move the intermediate code snippets 
further down the file.    

-----------------
SandBox - project
-----------------

Here is a project ready for you to experiment with CppUTest any my version of Unity

--------------------------
About Unity test framework
--------------------------

The version in the book is not the supported version maintained by the guys at
throwtheswitch.com.  If you want a supported version, please go to throwtheswitch.com




Please report any problems on the book's forum: www.pragprog.com/titles/jgade.

