# bash_info

Persistence of Xterm/Bash/Vim state on Window Manager cycling

## Introduction

I tend to have a lot of Xterms with Vim open on my system (Linux/Fedora). 
Every time I shutdown the Window Manager (KDE) and restarted it 
(generally, after a Yum update with a reboot), I would lose my
context; Xterms would open but only in my home directory and I
would not be in Vim. So, I wrote the following scripts that 
1) saved the current working directory and bash history on Xterm
shutdown and 2) on Window Manager restart of applications had
the Xterms determine what their working directories should be
and start Vim on the correct file, if there was a Vim session.

I wrote this, maybe, 10 years ago, but only now am I sharing.

## Getting started

Place the xterm script in your path prior to /usr/bin/xterm.
Mine is located in $HOME/bin/scripts/xterm but it is not 
important where it is, only that when you type 'xterm', it is
the script that runs.

Create a bash_info  directory  and make sure its location is the same
as that which appears in the xterm script.
    export BASH_INFO="$HOME/.bash_info"

Place the INIT_FILE in the bash_info directory.

## Important notes

Currently, for the xterm_{#} directories under the bash_info directory 
there is no cleanup/garbage-collection  if the xterm has exited
manually.

## TODO

How to remove an xterm_{id} file under the bash_info directory after
the associated xterm has been exited by the user (not exited because
of a Window Manager shutdown).

Maybe other xterm console applications,  not just Vim can be added to 
those that automatically on Window Manger resetart.
