---
title: "Variables"
teaching: 10
exercises: 0
questions:
- "How are variables set and accessed in the Unix shell?"
objectives:
- "Understand how variables are implemented in the shell"
- "Read the value of an existing variable"
- "Create new variables and change their values"
keypoints:
- "Shell variables are by default treated as strings"
- "Variables are assigned using \"`=`\" and recalled using the variable's name prefixed by \"`$`\""
---

(from https://www.tutorialspoint.com/unix/unix-using-variables.htm)
A variable is a character string to which we assign a value. The value assigned could be a number, text, filename, device, or any other type of data.

A variable is nothing more than a pointer to the actual data. The shell enables you to create, assign, and delete variables.

## Showing the Value of a Variable

Some variables are defined by default. Let's show the value of the variable `HOME`:

~~~
$ echo HOME
~~~
{: .bash}

~~~
HOME
~~~
{: .output}

That just prints "HOME", which isn't what we wanted
(though it is what we actually asked for).
Let's try this instead:

~~~
$ echo $HOME
~~~
{: .bash}

~~~
/home/vlad
~~~
{: .output}

The dollar sign tells the shell that we want the *value* of the variable
rather than its name.
This works just like wildcards:
the shell does the replacement *before* running the program we've asked for.
Thanks to this expansion, what we actually run is `echo /home/vlad`,
which displays the right thing.

## Creating and Changing Variables

Creating a variable is easy&mdash;we just assign a value to a name using "=":

~~~
$ SECRET_IDENTITY=Dracula
$ echo $SECRET_IDENTITY
~~~
{: .bash}

~~~
Dracula
~~~
{: .output}

To change the value, just assign a new one:

~~~
$ SECRET_IDENTITY=Camilla
$ echo $SECRET_IDENTITY
~~~
{: .bash}

~~~
Camilla
~~~
{: .output}

If we want to set some variables automatically every time we run a shell,
we can put commands to do this in a file called `.bashrc` in our home directory.
(The '.' character at the front prevents `ls` from listing this file
unless we specifically ask it to using `-a`:
we normally don't want to worry about it.
The "rc" at the end is an abbreviation for "run control",
which meant something really important decades ago,
and is now just a convention everyone follows without understanding why.)

For example,
here are two lines in `/home/vlad/.bashrc`:

~~~
export SECRET_IDENTITY=Dracula
export TEMP_DIR=/tmp
export BACKUP_DIR=$TEMP_DIR/backup
~~~
{: .output}

These three lines create the variables `SECRET_IDENTITY`,
`TEMP_DIR`,
and `BACKUP_DIR`,
and export them so that any programs the shell runs can see them as well.
Notice that `BACKUP_DIR`'s definition relies on the value of `TEMP_DIR`,
so that if we change where we put temporary files,
our backups will be relocated automatically.
