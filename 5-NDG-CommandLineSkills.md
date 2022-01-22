# NDG Linux Essentials

## Chapter 5 Command Line Skills

This chapter will cover the following exam objectives:

2.1: Command Line Basics

Weight: 3

Basics of using the Linux command line.

Key Knowledge Areas:

    Basic shell: Section 5.2
    Command line syntax: Section 5.3
    Variables: Section 5.4
    Quoting: Section 5.6

### 5.2 S

The shell is the command line interpreter that translates commands entered by a user into actions to be performed by the operating system.

The Linux environment allows the use of many different shells, some of which have been around for many years. The most commonly-used shell for Linux distributions is called the Bash shell. Bash provides many advanced features, such as command history and inline editing, which allows a user to easily re-execute previously executed commands or a variation of them via simple editing.

The Bash shell also has other popular features, a few of which are listed below:

* **Scripting**: The ability to place commands in a file and then interpret (effectively use Bash to execute the contents of) the file, resulting in all of the commands being executed. This feature also has some programming features, such as conditional statements and the ability to create functions (AKA subroutines).
* **Aliases**: The ability to create short nicknames for longer commands.
* **Variables**: Used to store information for the Bash shell and for the user. These variables can be used to modify how commands and features work as well as provide vital system information.

**The ~ symbol is used as shorthand for the user's home directory. Typically the home directory for the user is under the /home directory and named after the user account name;** 
**for example, /home/sysadmin**.

### 5.3 Commands

The typical format for a command is as follows:

command [options] [arguments]

**Options are used to modify the core behavior of a command while arguments are used to provide additional information** (such as a filename or a username). Each option and argument is normally separated by a space, although options can often be combined.

**Keep in mind that Linux is case-sensitive. Commands, options, arguments, variables, and file names must be entered exactly as shown.**

#### 5.3.1 Arguments

command [options] **[arguments]**

An argument can be used to specify something for the command to act upon. If the ls command is given the name of a directory as an argument, it lists the contents of that directory. In the following example, the /etc/ppp directory is used as an argument; the resulting output is a list of files contained in that directory: ls /etc/ppp

The ls command also accepts multiple arguments. To list the contents of both the /etc/ppp and /etc/ssh directories, pass them both as arguments: ls /etc/ppp /etc/ssh     

#### 5.3.2 Options 

command **[options]** [arguments]

Options can be used with commands to expand or modify the way a command behaves. For example, using the -l option of the ls command results in a long listing, providing additional information about the files that are listed, such as the permissions, the size of the file and other information: ls -l (long listing), ls -r (reversing list)

#### 5.3.3 History

When a command is executed in the terminal, it is stored in a history list. This is designed to make it easy to execute the same command, later eliminating the need to retype the entire command.

Pressing the Up Arrow ↑ key displays the previous command on the prompt line. The entire history of commands run in the current session can be displayed by pressing Up repeatedly to move back through the history of commands that have been run. Pressing the Enter key runs the displayed command again.

When the desired command is located, the Left Arrow ← and Right Arrow → keys can position the cursor for editing. Other useful keys for editing include the Home, End, Backspace and Delete keys.

**To view the history list of a terminal, use the history command**:

To view the history list of a terminal, **use the history command**;

If the desired command is in the list that the history command generates, **it can be executed by typing an exclamation point ! character and then the number next to the command**.

If the history command is passed **a number as an argument**, **it outputs that number of previous commands from the history list**.

**To execute the nth command from the bottom of the history list**, **type !-n and hit Enter**.

**To execute the most recent command type !! and hit Enter**

**To execute the most recent iteration of a specific command**, **type ! followed by the name of the command and hit Enter**. for instance: !ls

## 5.4 Variables

A variable is a feature that allows the user or the shell to store data. This data can be used to provide critical system information or to change the behavior of how the Bash shell (or other commands) work. Variables are given names and stored temporarily in memory. There are two types of variables used in the Bash shell: local and environment. 

### 5.4.1 Local Variables

**Local or shell variables exist only in the current shell**, and cannot affect other commands or applications. When the user closes a terminal window or shell, all of the variables are lost. They are often associated with user-based tasks and are lowercase by convention.

To set the value of a variable, use the following assignment expression. If the variable already exists, the value of the variable is modified. If the variable name does not already exist, the shell creates a new local variable and sets the value:

**variable1='Something'**

The echo command is used to display output in the terminal. To display the value of the variable, use a dollar sign $ character followed by the variable name as an argument to the echo command: echo $variable1

### 5.4.2 Environment Variables

Environment variables, also called global variables, **are available system-wide, in all shells used by Bash when interpreting commands and performing tasks**. The **system automatically recreates environment variables when a new shell is opened**. Examples include the **PATH, HOME, and HISTSIZE variables**. The **HISTSIZE variable defines how many previous commands to store in the history list**. The command in the example below displays the value of the HISTSIZE variable:

To modify the value of an existing variable, use the assignment expression:

HISTSIZE=500
echo $HISTSIZE

Many variables are available for the Bash shell, as well as variables that affect different Linux commands. A discussion of all variables is beyond the scope of this chapter; however, more shell variables will be covered as this course progresses.

When run without arguments, the **env command outputs a list of the environment variables**. Because the output of the env command can be quite long, the following examples use a text search to filter that output.

In a previous example variable1 was created as a local variable, so the following search in the environment variables results in no output.


The **pipe | character passes the output of the env command to the grep command, which searches the output**. This text filtering technique will be covered in detail later in the course.

**The export command is used to turn a local variable into an environment variable**. 

**The export command can also be used to make a variable an environment variable upon its creation by using the assignment expression as the argument**.

**To change the value of an environment variable, use the assignment expression**.
**Exported variables can be removed using the unset command**.

### 5.4.3 Path Variable

**One of the most important Bash shell variables to understand is the PATH variable. It contains a list that defines which directories the shell looks in to find commands. If a valid command is entered and the shell returns a "command not found" error, it is because the Bash shell was unable to locate a command by that name in any of the directories included in the path. The following command displays the path of the current shell**:

echo $PATH 

Each directory in the list is separated by a colon : character. Based on the preceding output, the path contains the following directories. The shell will check the directories in the order they are listed.

**If the command is not found in any directory listed in the PATH variable, then the shell returns an error**.

If **custom software is installed on the system it may be necessary to modify the PATH to make it easier to execute these commands**. For example, the following will add and verify the /usr/bin/custom directory to the PATH variable.

**When updating the PATH variable, always include the current path, so as not to lose access to commands located in those directories. This can be accomplished by appending $PATH to the value in the assignment expression. Recall that a variable name preceded by a dollar sign represents the value of the variable**.

### 5.5 Command Types

One way to learn more about a command is to look at where it comes from. The type command can be used to determine information about command type.

type command

There are several different sources of commands within the shell of your CLI including internal commands, external commands, aliases, and functions.

#### 5.5.1 Internal Commands

Also **called built-in commands, internal commands are built into the shell itself**. A **good example is the cd (change directory) command as it is part of the Bash shell**. When a user types the cd command, the **Bash shell is already executing and knows how to interpret it**, requiring no additional programs to be started.

The type command identifies the cd command as an internal command: type cd 

#### 5.5.2 External Commands

**External commands are binary executables stored in directories that are searched by the shell**. If **a user types the ls command, then the shell searches through the directories that are listed in the PATH variable to try to find a file named ls that it can execute**.

If **a command does not behave as expected or if a command is not accessible that should be, it can be beneficial to know where the shell is finding the command or which version it is using**. It **would be tedious to have to manually look in each directory that is listed in the PATH variable**. Instead, **use the which command to display the full path to the command in question**: which command.

The which command searches for the location of a command by searching the PATH variable.

which ls
which cal

External commands can also be executed by typing the complete path to the command. For example, to execute the ls command: /bin/ls

For external commands, the **type command displays the location of the command**.
**In some cases the output of the type command may differ significantly from the output of the which command**.

type -a ls

#### 5.5.3 Aliases

An **alias can be used to map longer commands to shorter key sequences**. **When the shell sees an alias being executed, it substitutes the longer sequence before proceeding to interpret commands**.

For example, the** command **ls -l is commonly aliased to l or ll****. Because these smaller commands are easier to type, it becomes faster to run the ls -l command line.

**To determine what aliases are set on the current shell use the alias command**.

**New aliases can be created using the following format, where name is the name to be given the alias and command is the command to be executed when the alias is run.**

**alias name=command**

**Aliases created this way only persist while the shell is open. Once the shell is closed, the new aliases are lost**. Additionally, each shell has its own aliases, so aliases created in one shell won’t be available in a new shell that’s opened.

**The type command can identify aliases to other commands**.

#### 5.5.4 Functions

Functions can also be built using existing commands to either create new commands, or to override commands built-in to the shell or commands stored in files. Aliases and functions are normally loaded from the initialization files when the shell first starts.

Functions are more advanced than aliases and typically are used in Bash shell scripts. Typically, functions are used to execute multiple commands. To create a function, the following syntax is used:

function_name () 
{
   commands
}

In the format above, function_name can be anything that the administrator wants to call the function. The commands that the administrator wants to execute can replace the commands placeholder. Note the formatting, in particular, the location of the parenthesis () and braces {}, as well as the convention of using tabs to make the function more easily readable.

**Functions are useful as they allow for a set of commands to be executed one at a time instead of typing each command repeatedly**. In the example below, a function called my_report is created to execute the ls, date, and echo commands.

When creating a function, a > character will appear as a prompt to enter the commands for the function. The curly braces {} are used to let the shell know when a function begins and ends so as to exit the > prompt.

Once a function is created, the function name may be invoked from the BASH prompt to execute the function:

### 5.6 Quoting

Quotation **marks are used throughout Linux administration and most computer programming languages to let the system know that the information contained within the quotation marks should either be ignored or treated in a way that is very different than it would normally be treated**. There are three types of quotes that have special significance to the Bash shell: double quotes ", single quotes ', and back quotes `. Each set of quotes alerts the shell not to treat the text within the quotes in the normal way.

#### 5.6.1 Double Quotes

Double quotes stop the shell from interpreting some metacharacters (special characters), including glob characters. 

Glob characters, also called wild cards, are symbols that have special meaning to the shell; they are interpreted by the shell itself before it attempts to run any command. Glob characters include the asterisk * character, the question ? mark character, and the brackets [ ], among others. 

Within double quotes an asterisk is just an asterisk, a question mark is just a question mark, and so on, which is useful when you want to display something on the screen that is normally a special character to the shell. In the echo command below, the Bash shell doesn't convert the glob pattern into filenames that match the pattern:

echo "The glob characters are *, ? and [ ]"

Double quotes still allow for command substitution, variable substitution, and permit some other shell metacharacters that haven't been discussed yet. The following demonstration shows that the value of the PATH variable is still displayed:

echo "The path is $PATH"

#### 5.6.2 Single Quotes

Single quotes prevent the shell from doing any interpreting of special characters, including globs, variables, command substitution and other metacharacters that have not been discussed yet.

For example, to make the $ character simply mean a $, rather than it acting as an indicator to the shell to look for the value of a variable, execute the second command displayed below:

echo The car costs $100   -> The car costs 00
echo 'The car costs $100' -> The car costs $100

#### 5.6.3 Backslash Character

There is also an alternative technique to essentially single quote a single character. Consider the following message: 

The service costs $1 and the path is $PATH 

If this sentence is placed in double quotes, $1 and $PATH are considered variables. 

echo "The service costs $1 and the path is $PATH" -> ‌⁠​​⁠​The service costs  and the path is /usr/bin/custom:/home/sysadmin/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games 

If it is placed in single quotes, $1 and $PATH are not considered variables. 

echo 'The service costs $1 and the path is $PATH' -> The service costs $1 and the path is $PATH 

But what if you want to have $PATH treated as a variable and $1 not?

In this case, use a backslash \ character in front of the dollar sign $ character to prevent the shell from interpreting it. The command below demonstrates using the \ character:

echo The service costs \$1 and the path is $PATH -> The service costs $1 and the path is /usr/bin/custom:/home/sysadmin/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games

#### 5.6.4 Backquotes

Backquotes, or backticks, are used to specify a command within a command, a process called command substitution. This allows for powerful and sophisticated use of commands.

While it may sound confusing, an example should make things more clear. To begin, note the output of the date command:

date -> Mon Nov  4 03:35:50 UTC 2018

Now, note the output of the echo command:

echo Today is date -> Today is date

In the previous command, the word date is treated as regular text, and the shell passes date to the echo command. To execute the date command and have the output of that command sent to the echo command, put the date command in between two backquote characters:

sysadmin@localhost:~$ echo Today is `date`                         
Today is Mon Nov 4 03:40:04 UTC 2018

### 5.7 Control Statements

Control statements allow you to use multiple commands at once or run additional commands, depending on the success of a previous command. Typically these control statements are used within scripts, but they can also be used on the command line as well.

#### 5.7.1 Semicolon

command1; command2; command3

The semicolon ; character can be used to run multiple commands, one after the other. Each command runs independently and consecutively; regardless of the result of the first command, the second command runs once the first has completed, then the third and so on.

cal 1 2030; cal 2 2030; cal 3 2030

#### 5.7.2 Double Ampersand

command1 && command2

The double ampersand && **acts as a logical "and"**; if the first command is successful, then the second command will also run. If the first command fails, then the second command will not run.

To better understand how this works, consider first the concept of failure and success for commands. Commands succeed when they work properly and fail when something goes wrong. For example, consider the ls command. The command succeeds if the given directory is accessible and fails if it isn't.

In the following example, the first command succeeds because the /etc/ppp directory exists and is accessible while the second command fails because there is no /junk directory.

To use the success or failure of the ls command in conjunction with && execute commands like the following. In the first example, the echo command is executed because the ls command succeeds.

#### 5.7.3 Double Pipe

command1 || command2

The double pipe || is a logical "or". Depending on the result of the first command, the second command will either run or be skipped.

With the double pipe, if the first command runs successfully, the second command is skipped; if the first command fails, then the second command is run. In other words, you are essentially telling the shell, "Either run this first command or the second one”.

In the following example, the echo command only executes if the ls command fails:

### Key terms

**Bash**: The most commonly used shell for Linux distributions. Section 5.2 
**PATH environment variable**: Variable containing a list that defines which directories the shell looks in for commands. Section 5.4.3 
**echo**: Command that displays output in the terminal. Section 5.4.1 
**export**: Command that turns a local variable into an environment variable. Section 5.4.2 
**history**: Command that outputs a list of previously executed commands. Section 5.3.3 
**type**: Command that determines information about command type. Section 5.5 



