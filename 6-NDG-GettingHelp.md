# NDG Linux Essentials

This chapter will cover the following exam objectives:

2.2: Using the Command Line to Get Help

Weight: 2

Running help commands and navigation of the various help systems.

Key Knowledge Areas:
* Info pages Section 6.4
* Man pages  Section 6.2

## Chapter 6 Getting Help

### 6.2.1 Viewing Man Pages

To exit viewing a man page, use the Q key.

**Consider This**

The man command uses a pager to display documents. Usually, this pager is the less command, but on some distributions, it may be the more command. Both are very similar in how they perform. To view the various movement commands that are available, use the H key while viewing a man page. This displays a help page. Pagers will be discussed in more detail later in the course.

### 6.2.2 Sections Within Man Pages

Man pages are broken into sections. Each section is designed to provide specific information about a command. While there are common sections seen in most man pages, some developers also create sections only available on specific man pages.

The following describes some of the more common sections found in man pages:

* name: Provides the name of the command and a very brief description.
* SYNOPSIS: Provides examples of how the command is executed. The SYNOPSIS section of a man page can be difficult to understand but **is very important because it provides a concise example of how to use the command**. For example, consider the SYNOPSIS of the man page for the cal command: cal [-31jy] [-A number] [-B number] [-d yyyy-mm] [[month] year]. The square brackets [ ] are used to indicate that this feature is not required to run the command. For example, [-31jy] means options -3, -1, -j, or -y are available, but not required for the cal command to function properly. The last set of square brackets [[month] year] demonstrates another feature; it means a year can be specified by itself, but to specify a month the year must also be specified. Another component of the SYNOPSIS that might cause some confusion can be seen in the man page of the date command:   date [OPTION]... [+FORMAT]                                      
date [-u|--utc|--universal] [MMDDhhmm[[CC]YY][.ss]]. In this SYNOPSIS there are two syntaxes for the date command. The first one is used to display the date on the system while the second is used to set the date. The ellipsis ... following [OPTION] indicates that one or more of the items before it may be used. Additionally, the [-u|--utc|--universal] notation means that either the -u option or the --utc option or the --universal option may be used. Typically this means that all three options really do the same thing, but sometimes the use of the | character is used to indicate that the options can't be used in combination, like a logical “or".

* DESCRIPTION: Provides a more detailed description of the command.
* OPTIONS: Lists the options for the command as well as a description of how they are used. Often this information is found in the DESCRIPTION section and not in a separate OPTIONS section.
* FILES: Lists the files that are associated with the command as well as a description of how they are used. These files may be used to configure the command's more advanced features. Often this information is found in the DESCRIPTION section and not in a separate FILES section.
* AUTHOR: Provides the name of the person who created the man page and (sometimes) how to contact the person.
* REPORTING BUGS: Provides details on how to report problems with the command.
* COPYRIGHT: Provides basic copyright information.
* SEE ALSO
  
### 6.2.3 Searching Man Pages

To search a man page for a term, **type the / character followed by a search term**, then hit the Enter key. The program searches from the current location down towards the bottom of the page to try to locate and highlight the term.

If a match is found, **it will be highlighted**. To move to the next match of the term, ***press n***. To return to a previous match of the term, **press Shift+N**. If the term is not found, or upon reaching the end of the matches, the program will report Pattern not found (press Return).

### 6.2.4 Man Pages Categorized by Sections

Until now, we have been displaying man pages for commands. However, **there are several different types of commands (user commands, system commands, and administration commands)**, configuration files and other features, such as libraries and kernel components, that require documentation.

As a result, there are thousands of man pages on a typical Linux distribution. To organize all of these man pages, they are categorized by sections.

By default, there are nine sections of man pages:

1. General Commands
2. System Calls
3. Library Calls
4. Special Files
5. File Formats and Conventions
6. Games
7. Miscellaneous
8. System Administration Commands
9. Kernel Routines

The man command searches each of these sections in order until it finds the first match. For example, if you execute the command man cal, the first section (General Commands) is searched for a man page called cal. If not found, then the second section is searched. If no man page is found after searching all sections, an error message is returned:

No manual entry for zed

To determine which section a specific man page belongs to, look at the numeric value on the first line of the output of the man page. For example, the cal command belongs to the first section of man pages: CAL(1)                    BSD General Commands Manual             CAL(1)

Sometimes there are man pages with the same name in different sections. In these cases, it may be necessary to specify the section of the correct man page.

For example, there is a command called passwd that allows you to change your password. There is also a file called passwd that stores account information. Both the command and the file have a man page.

The passwd command is a user command, so the associated man page is in the first section. The man command displays the man page for the passwd command by default:

man passwd

PASSWD(1)                        User Commands                 PASSWD(1)

So how do you display the man page for the passwd file? First, determine in which section the man page is located. To search for man pages by name, use the -f option to the man command. It displays man pages that match, or partially match, a specific name and provide the section number and a brief description of each man page:

sysadmin@localhost:~$ man -f passwd                                    
passwd (5)           - the password file                              
passwd (1)           - change user password                           
passwd (1ssl)        - compute password hashes         

Note: On most Linux distributions, the **whatis command**** does the same thing as man -f**. On those distributions, both will produce the same output.

To specify a different section, provide the number of the section as the first argument of the man command. The following command displays the passwd man page located in section 5, which is associated with the passwd file:

sysadmin@localhost:~$ man 5 passwd

PASSWD(5)                File Formats and Conversions          PASSWD(5)

Unfortunately, you won't always remember the exact name of the man page that you want to view. Fortunately, each man page has a short description associated with it. The -k option to the man command searches both the names and descriptions of the man pages for a keyword.

For example, to find a man page that displays how to copy directories, search for the keyword copy:

sysadmin@localhost:~$ man -k copy                                               
cp (1)               - copy files and directories                               
cpgr (8)             - copy with locking the given file to the password or gr...
cpio (1)             - copy files to and from archives                          
cppw (8)             - copy with locking the given file to the password or gr...
dd (1)               - convert and copy a file                                  
debconf-copydb (1)   - copy a debconf database                                  
install (1)          - copy files and set attributes                            
scp (1)              - secure copy (remote file copy program)                   
ssh-copy-id (1)      - use locally available keys to authorize logins on a re...

Recall that there are thousands of man pages, so when searching for a keyword, be as specific as possible. Using a generic word, such as "the", could result in hundreds or even thousands of results.
Note: On most Linux distributions, the **apropos command does the same thing as man -k**. On those distributions, both produce the same output.

## 6.3 Finding Commands and Documentation

The **whatis command (or man -f) returns what section a man page is stored in**. This command occasionally returns unusual output, such as the following:

sysadmin@localhost:~$ whatis ls                                              
ls (1)               - list directory contents 
ls (lp)              - list directory contents

Note

The **example above is designed to demonstrate a scenario where two commands list directory contents**. The output in the example terminal above may not match the output in the VM.

Based on this output, there are two ls commands that list directory contents. The simple reason for this is that UNIX had two main variants, which resulted in some commands being developed "in parallel" and therefore behaving differently on different variants of UNIX. Many modern distributions of Linux include commands from both UNIX variants.

This does, however, pose a bit of a problem: when the ls command is typed, which command is executed?

### 6.3.1 Where Are These Commands Located?

To search for the location of a command or the man pages for a command, **use the whereis command**. This command searches for commands, source files and man pages in specific locations where these files are typically stored:

sysadmin@localhost:~$ whereis ls 
ls: /bin/ls /usr/share/man/man1p/ls.1.gz /usr/share/man/man1/ls.1.gz

**Man pages are easily distinguished from commands as they are typically compressed with a program called gzip**, resulting in a filename that ends in .gz. Notice **there are two man pages listed above, but only one command: /bin/ls**. This is because the ls command can be used with the options/features that are described by either man page. So, when learning what can be done with the ls command, it may be interesting to explore both man pages. Fortunately, this is more of an exception as most commands only have one man page.

### 6.3.2 Find Any File or Directory

The **whereis command is specifically designed to find commands and man pages**. While this is useful, **it is often necessary to find a file or directory, not just files that are commands or man pages**.

**To find any file or directory, use the locate command**. This command searches a database of all files and directories that were on the system when the database was created. Typically, the command to generate this database is run nightly.

sysadmin@localhost:~$ locate gshadow                                   
/etc/gshadow                                                           
/etc/gshadow-                                                          
/usr/include/gshadow.h                                                
/usr/share/man/cs/man5/gshadow.5.gz                                   
/usr/share/man/da/man5/gshadow.5.gz                                    
/usr/share/man/de/man5/gshadow.5.gz                                    
/usr/share/man/fr/man5/gshadow.5.gz                                    
/usr/share/man/it/man5/gshadow.5.gz                                    
/usr/share/man/man5/gshadow.5.gz                                       
/usr/share/man/ru/man5/gshadow.5.gz                                   
/usr/share/man/sv/man5/gshadow.5.gz                                    
/usr/share/man/zh_CN/man5/gshadow.5.gz                                 

Any files created today will not be searchable with the locate command. If root access is available, it’s possible to update the locate database manually by running the **updatedb command**. Regular users cannot update the database file.

Also note that when using the **locate command as a regular user, the output may be limited due to file permissions**. **If the user that is logged in doesn’t have access to a file or directory on the filesystem due to permissions, the locate command won't return those names**. **This security feature is designed to keep users from "exploring" the filesystem by using the locate database**. **The root user can search for any file in the locate database**.

The output of the locate command can be quite large. When searching for a filename, such as passwd, the locate command produces every file that contains the string passwd, not just files named passwd.

In many cases, it is helpful to start by finding out how many files match. **Do this by using the -c option to the locate command**:

sysadmin@localhost:~$ locate -c passwd                                 
98

To limit the output produced by the locate **command use the -b option**. This option only includes listings that have the search term in the basename of the filename. The basename is the portion of the filename not including the directory names.

sysadmin@localhost:~$ **locate -c -b passwd**                              
83                                                                     

As you can see from the previous output, there will still be many results when the -b option is used. To limit the output even further, place a \ character in front of the search term. This character limits the output to filenames that exactly match the term:

sysadmin@localhost:~$ locate -b "\passwd"                              
/etc/passwd                                                                     
/etc/pam.d/passwd                                                               
/usr/bin/passwd                                                                 
/usr/share/doc/passwd                                                           
/usr/share/lintian/overrides/passwd

## 6.4 Info Documentation

Man pages are excellent sources of information, but they do tend to have a few disadvantages. One example **is that each man page is a separate document, not related to any other man page**. While some man pages have a SEE ALSO section that may refer to other man pages, they tend to be independent sources of documentation.

**The info command also provides documentation on operating system commands and features. The goal is slightly different from man pages: to provide a documentation resource that gives a logical organizational structure, making reading documentation easier.**

All of the documentation is merged into a single "book" representing all of the documentation available. Within info documents, information is broken down into categories that work much like a table of contents in a book. Hyperlinks are provided to pages with information on individual topics for a specific command or feature.

Another advantage of info over man pages is that the writing style of info documents is typically more conducive to learning a topic. Consider man pages to be more of a reference resource and info documents to be more of a learning guide.

### 6.4.1 Viewing Info Documentation

To display the info documentation for a command, use the **info command**. For example, to display the info page of **the ls command**; Navigate the document **using the arrow keys**:

**This documentation is broken up into nodes, and in the example above the line highlighted in white shows it’s currently in the ls invocation node**. The first line provides index information about the current location within the document. The next node, like the next chapter in a book, would be the dir invocation node. Going up one level is the Directory listing node.

Scrolling through the document, notice the menu for the ls command;

The items under the menu are hyperlinks that link to nodes that describe more about the ls command. For example, placing the cursor on the line * Sorting the output:: and pressing the Enter key, leads to a node that describes sorting the output of the ls command:

**Note that going into the node about sorting leads into a sub-node of the original. To go back to the previous node, use the U key. While U leads to the start of the node one level up, the L key returns to the same location as before entering the sorting node**.

### 6.4.2 Navigating Info Documents

Like the man command, a listing of movement commands is available by hitting the Shift+H key while reading the info documentation:

Basic Info command keys                                                         
                                                                                
l           Close this help window.                                             
q           Quit Info altogether.                                               
h           Invoke the Info tutorial.                                           
                                                                                
Up          Move up one line.                                                   
Down        Move down one line.                                                 
PgUp        Scroll backward one screenful.                                      
PgDn        Scroll forward one screenful.                                       
Home        Go to the beginning of this node.                                   
End         Go to the end of this node.                                         
                                                                                
TAB         Skip to the next hypertext link.                                    
RET         Follow the hypertext link under the cursor.                         
l           Go back to the last node seen in this window.                       
                                                                                
[           Go to the previous node in the document.                            
]           Go to the next node in the document.                                
p           Go to the previous node on this level.                              
n           Go to the next node on this level.                                  
u           Go up one level.                                                    
-----Info: *Info Help*, 302 lines -- Top--------------------------------------

Note that to close the help screen type the L key, which brings back the current document. To quit entirely, use the Q key.

### 6.4.3 Exploring Info Documentation

Instead of using info documentation to look up information about a specific command or feature, consider exploring the capabilities of Linux by reading through the info documentation. Execute the info command without any arguments to be taken to the top level of the documentation. This is a good starting point to explore many of the features offered:

File: dir,      Node: Top,      This is the top of the INFO tree.               
                                                                                
This is the Info main menu (aka directory node).                                
A few useful Info commands:                                                     
                                                                                
  'q' quits;                                                                    
  'H' lists all Info commands;                                                  
  'h' starts the Info tutorial;                                                 
  'mTexinfo RET' visits the Texinfo manual, etc.                                
                                                                                
* Menu:                                                                         
                                                                                
Basics                                                                          
* Common options: (coreutils)Common options.                                    
* Coreutils: (coreutils).       Core GNU (file, text, shell) utilities.         
* Date input formats: (coreutils)Date input formats.                            
* File permissions: (coreutils)File permissions.                                
                                Access modes.                                   
* Finding files: (find).        Operating on files matching certain criteria.   
                                                                                
C++ libraries                                                                   
* autosprintf: (autosprintf).   Support for printf format strings in C++.       
-----Info: (dir)Top, 211 lines --Top--------------------------------------------
Welcome to Info version 6.5.  Type H for help, h for tutorial. 


### 6.5.1 Using the Help Option

Many commands will provide basic information, very similar to the SYNOPSIS found in man pages, by simply using the --help option to the command. This option is useful to learn the basic usage of a command quickly without leaving the command line:

sysadmin@localhost:~$  cat --help                                                
Usage: cat [OPTION]... [FILE]...                                                
Concatenate FILE(s) to standard output.                                         
                                                                                
With no FILE, or when FILE is -, read standard input.                           
                                                                                
  -A, --show-all           equivalent to -vET                                   
  -b, --number-nonblank    number nonempty output lines, overrides -n           
  -e                       equivalent to -vE                                    
  -E, --show-ends          display $ at end of each line                        
  -n, --number             number all output lines                              
  -s, --squeeze-blank      suppress repeated empty output lines                 
  -t                       equivalent to -vT                                    
  -T, --show-tabs          display TAB characters as ^I                         
  -u                       (ignored)                                            
  -v, --show-nonprinting   use ^ and M- notation, except for LFD and TAB        
      --help     display this help and exit                                     
      --version  output version information and exit                            
                                                                                
Examples:                                                                       
  cat f - g  Output f's contents, then standard input, then g's contents.       
  cat        Copy standard input to standard output.                            
                                                                                
GNU coreutils online help: <http://www.gnu.org/software/coreutils/>             
Report cat translation bugs to <http://translationproject.org/team/>            
Full documentation at: <http://www.gnu.org/software/coreutils/cat>              
or available locally via: info '(coreutils) cat invocation'  

### 6.5.2 Additional System Documentation

On most systems, there is a directory where additional documentation (such as documentation files stored by third-party software vendors) is found.
‌⁠​​

These documentation files are often called readme files since the files typically have names such as README or readme.txt. The location of these files can vary depending on the distribution that you are using. Typical locations include /usr/share/doc and /usr/doc.

Typically, this directory is where system administrators go to learn how to set up more complex software services. However, sometimes regular users also find this documentation to be useful.

## Key terms



/usr/share/doc/
    Directory containing additional documentation files, such as readme files and support for third-party software.
    Section 6.5.2 
info
    Command used to view info documentation for commands.
    Section 6.4.1 
locate
    Command used to find any file or directory. Relies on a database typically generated nightly.
    Section 6.3.2 
man
    Command used to view manual (man) pages for commands.
    Section 6.2.1 


