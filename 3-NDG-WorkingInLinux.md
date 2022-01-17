# NDG Linux Essentials

## Chapter 3

* Objectives
    1. Linux Evolution and Popular Operating Systems
        * weight 2
        * Knowledge of Linux development and major distributions.
        * Key Knowledge Areas: Linux in the Clouds Section 3.7.1
    1. Major Open Source Applications
        * weight 2
        * Awareness of major applications as well as their uses and development.
        * Key Knowledge Areas: Desktop applications Section 3.2.3; Server applications Section 3.2.2; Development languages Section 3.5; Package management tools and repositories Section 3.4
    1. ICT Skills and Working in Linux
        * weight 2
        * Basic Information and Communication Technology (ICT) skills and working in Linux.
        * Key Knowledge Areas:  Desktop skills Section 3.1;  Getting to the command line Section 3.1.1;  Industry uses of Linux, cloud computing and virtualization Section 3.7

### 3.1 Navigating the Linux Desktop

To be a Linux systems administrator, it is necessary **to be comfortable with Linux as a desktop OS and have proficiency with basic Information and Communication Technology (ICT) skills**.

Using Linux for productivity tasks it accelerates learning by working with Linux tools on a daily basis. **Systems administrators do far more than manage servers**; they are often called upon to assist users with configuration issues, recommend new software, and update documentation among other tasks. 

#### 3.1.1 Getting to the command line

The command line interface (CLI) is a simple text input system for entering anything from single-word commands to complicated scripts. Most operating systems have a CLI that provides a direct way of accessing and controlling the computer. 

On systems that boot to a GUI, there are two common ways of accessing the command line—a GUI-based terminal, and a virtual terminal:
    * A GUI terminal is a program within the GUI environment that emulates a terminal window. GUI terminals can be accessed through the menu system. For example, on a CentOS machine, you could click on Applications on the menu bar, then System Tools > and, finally, Terminal. If you have a search tools, you can search for terminal, as shown here.
    * A virtual terminal can be run at the same time as a GUI but requires the user to log in via the virtual terminal before they can execute commands (as they would before accessing the GUI interface).

Each Linux desktop distribution is slightly different, but the application terminal or x-term will open a terminal window from the GUI. While there are subtle differences between the terms console and terminal window sessions, they are all the same from an administrators standpoint and require the same knowledge of commands to use.

Ordinary command line tasks are starting programs, parsing scripts, and editing text files used for system or application configuration. Most servers boot directly to a terminal, as a GUI can be resource intensive and is generally not needed to perform server-based operations.‌⁠​​

### 3.2 Applications

The kernel of the **OS is like an air traffic controller at an airport**, and the **applications are the airplanes under its control**. The **kernel decides which program gets which blocks of memory**, it **starts and kills applications**, and **it handles displaying text or graphics on a monitor**.

Applications make requests to the kernel and in return receive resources, such as memory, CPU, and disk space. If **two applications request the same resource**, **the kernel decides which one gets it, and in some cases, kills off another application to save the rest of the system and prevent a crash**.

**The kernel also abstracts some complicated details away from the application**. **For example, the application doesn’t know if a block of disk storage is on a solid-state drive, a spinning metal hard disk, or even a network file share.** **Applications need only follow the kernel’s Application Programming Interface (API) and therefore don’t have to worry about the implementation details**. **Each application behaves as if it has a large block of memory on the system; the kernel maintains this illusion by remapping smaller blocks of memory, sharing blocks of memory with other applications, or even swapping out untouched blocks to disk.**

The **kernel also handles the switching of applications**, **a process known as multitasking**. A computer system has a small number of central processing units (CPUs) and a finite amount of memory. The kernel takes care of **unloading one task and loading a new one if there is more demand than resources available**. **When one task has run for a specified amount of time, the CPU pauses it so that another may run**. If the computer is doing several tasks at once, the **kernel is deciding when to switch focus between tasks**. With the tasks rapidly switching, it appears that the computer is doing many things at once.

When we, as users, think of applications, we tend to think of word processors, web browsers, and email clients, however, there are a large variety of application types. The kernel doesn’t differentiate between a user-facing application, a network service that talks to a remote computer, or an internal task. From this, **we get an abstraction called a process**. **A process is just one task that is loaded and tracked by the kernel**. An application may even need multiple processes to function, so the kernel takes care of running the processes, starting and stopping them as requested, and handing out system resources.

#### 3.2.1 Major Applications

The Linux kernel can run a wide variety of software across many hardware platforms. A computer can act as a server, which means it primarily handles data on others’ behalf, or as a desktop, which means a user interacts with it directly. The machine can run software or be used as a development machine in the process of creating software. **A machine can even adopt multiple roles as Linux makes no distinction; it’s merely a matter of configuring which applications run.**

One resulting advantage is that **Linux can simulate almost all aspects of a production environment, from development to testing, to verification on scaled-down hardware, which saves costs and time**. A **Linux administrator could run the same server applications on a desktop or inexpensive virtual server that are run by large internet service providers**. Of course, a desktop would not be able to handle the same volume as a major provider would, but almost any configuration can be simulated without needing powerful hardware or server licensing.

Linux software generally falls into one of three categories:

* Server Applications: Software that has no direct interaction with the monitor and keyboard of the machine it runs on. **Its purpose is to serve information to other computers**, called clients. Sometimes server applications may not talk to other computers but only sit there and crunch data.
* Desktop Applications: Web browsers, text editors, music players, or other applications with which users interact directly. In many cases, such as a web browser, **the application is talking to a server on the other end and interpreting the data**. This is the “client” side of a client/server application.
* Tools: A loose category of software that exists to make it easier to manage computer systems. **Tools can help configure displays, provide a Linux shell that users type commands into, or even more sophisticated tools, called compilers, that convert source code to application programs that the computer can execute**.

The availability of applications varies depending on the distribution. Often application vendors choose a subset of distributions to support. Different distributions have different versions of key libraries, and it is difficult for a company to support all these different versions. Some applications, however, like Firefox and LibreOffice are widely supported and available for all major distributions.

**The Linux community has come up with lots of creative solutions for both desktop and server applications**. These applications, many of which make up the backbone of the Internet, **are critical to understanding, and utilizing the power of Linux**.

Most computing tasks can be accomplished by any number of applications in Linux. There are many web browsers, web servers, database servers, and text editors from which to choose. Evaluating application software is an important skill to be learned by the aspiring Linux administrator. Determining requirements for performance, stability, and cost are just some of the considerations needed for a comprehensive analysis.

#### 3.2.2 Server applications

Linux excels at running server applications because of **its reliability and efficiency**. The **ability to optimize server OS with just needed components allows administrators to do more with less**, a feature loved by startups and large enterprises alike.

1. **Web servers**: One of the early uses of Linux **was for web servers**. A web server hosts content for web pages, which are viewed by a web browser using the HyperText Transfer Protocol (HTTP) or its encrypted flavor, HTTPS. The web page itself can either be static or dynamic. When the web browser requests a static page, the web server sends the file as it appears on disk. In the case of a dynamic site, the request is sent by the web server to an application, which generates the content. **Apache is the dominant web server in use today**. Apache was originally a standalone project, but the group has since formed the Apache Software Foundation and maintains over a hundred open source software projects. **Apache HTTPD is the daemon, or server application program, that “serves” web page requests**. Another web server **is NGINX**, which is based out of Russia. It focuses on performance by making use of more modern UNIX kernels and only does a subset of what Apache can do. **Over 65% of websites are powered by either NGINX or Apache**.
1. **Private Cloud Servers**: As individuals, organizations, and companies start to move their data to the cloud, **there is a growing demand for private cloud server software that can be deployed and administered internally**. The **ownCloud project** was launched in 2010 by Frank Karlitschek to provide software to store, sync and share data from private cloud servers. It is available in a standard open source GNU AGPLv3 license and an enterprise version that carries a commercial license. The **Nextcloud project** was forked from ownCloud in 2016 by Karlitschek and has been growing steadily since then. It is provided under a GNU AGPLv3 and aims for “an open, transparent development process.” **Both projects focus on providing private cloud software that meets the needs of both large and small organizations that require security, privacy, and regulatory compliance**. While several other projects aim to serve the same users, these two are by far the largest in terms of both deployment and project members.
1. **Database servers**: **Database server applications form the backbone of most online services**. **Dynamic web applications pull data from and write data to these applications**. For example, **a web program for tracking online students might consist of a front-end server that presents a web form**. When data is entered into the form, it is written to a database application such as MariaDB. When instructors need to access student information, the web application queries the database and returns the results through the web application. **MariaDB is a community-developed fork of the MySQL relational database management system**. It is just one of many database servers used for web development as different requirements dictate the best application for the required tasks. **A database stores information and also allows for easy retrieval and querying**. Some other popular databases are Firebird and PostgreSQL. You might enter raw sales figures into the database and then use a language called Structured Query Language (SQL) to aggregate sales by product and date to produce a report.
1. **Email servers**: **Email has always been a widespread use for Linux servers**. When discussing email servers, it is always helpful to look at the 3 different tasks required to get email between people: **Mail Transfer Agent (MTA)**: The most well known MTA (software that is used to transfer electronic messages to other systems) is Sendmail. Postfix is another popular one and aims to be simpler and more secure than Sendmail; **Mail Delivery Agent (MDA)**: Also called the Local Delivery Agent, it takes care of storing the email in the user’s mailbox.  Usually invoked from the final MTA in the chain; **POP/IMAP Server**: The Post Office Protocol (POP) and Internet Message Access Protocol (IMAP) are two communication protocols that let an email client running on your computer talk to a remote server to pick up the email. **Dovecot is** a popular POP/IMAP server owing to its ease of use and low maintenance. **Cyrus IMAP** is another option. Some POP/IMAP servers implement their own mail database format for performance and include the MDA if the custom database is desired. People using standard file formats (such as all the emails in one text file) can choose any MDA. There are several significant differences between the closed source and open source software worlds, one being that of inclusion of other projects as components to a project or package. **In the closed source world**, Microsoft Exchange is shipped primarily as a software package/suite that includes all the necessary or approved components, all from Microsoft, so there are few if any options to make individual selections. **In the open source world**, many options can be modularly included or swapped out for package components, and indeed some software packages or suites are just a well-packaged set of otherwise individual components all harmoniously working together.
1. **File sharing**: For Windows-centric file sharing, **Samba is the clear winner**. **Samba allows a Linux machine to look and behave like a Windows machine so that it can share files and participate in a Windows domain**. **Samba implements the server components, such as making files available for sharing and certain Windows server roles, and also the client end so that a Linux machine may consume a Windows file share**. **The Netatalk project lets** a Linux machine perform as an Apple Macintosh file server. **The native file sharing protocol for UNIX/Linux is called the Network File System (NFS)**. NFS is usually part of the kernel which means that a remote file system can be mounted (made accessible) just like a regular disk, making file access transparent to other applications. As a computer network becomes more substantial, the need for a directory increases. **One of the oldest network directory systems is the Domain Name System (DNS)**. It is used to convert a name like https://www.icann.org/ to an IP address like 192.0.43.7, which is a unique identifier of a computer on the Internet. **DNS also holds global information like the address of the MTA for a given domain name**. An organization may want to run their own DNS server to host their public-facing names, and also to serve as an internal directory of services. The Internet Software Consortium maintains the most popular DNS server, simply called bind after the name of the process that runs the service. **The DNS is focused mainly on computer names and IP addresses and is not easily searchable**. Other directories have sprung up to store information such as user accounts and security roles. The **Lightweight Directory Access Protocol (LDAP) is one common directory system which also powers Microsoft’s Active Directory**. **In LDAP**, **an object is stored in a tree, and the position of that object on the tree can be used to derive information about the object and what it stores**. For example, a Linux administrator may be stored in a branch of the tree called “IT Department,” which is under a branch called “Operations.” Thus one can find all the technical staff by searching under the “IT Department” branch. OpenLDAP is the dominant program used in Linux infrastructure. One final piece of network infrastructure to discuss here is called the **Dynamic Host Configuration Protocol (DHCP)**. When a computer boots up, **it needs an IP address for the local network so it can be uniquely identified**. **DHCP’s job is to listen for requests and to assign a free address from the DHCP pool**. The Internet Systems Consortium (known until January 2004 as the Internet Software Consortium) also maintains the ISC DHCP server, which is the most common open source DHCP server.

#### 3.2.3 Desktop applications

The Linux ecosystem has a wide variety of desktop applications. There are games, productivity applications, creative tools, web browsers and more.

1. **email**: The Mozilla Foundation came out with **Thunderbird**, a full-featured desktop email client. **Thunderbird connects to a POP or IMAP server**, displays email locally, and sends email through an external SMTP server. Other notable email clients are **Evolution and KMail which are the GNOME and KDE projects' email clients**. Standardization through POP and IMAP and local email formats means that it’s easy to switch between email clients without losing data. 
1. **Creative**: For the creative types, there is **Blender, GIMP** (GNU Image Manipulation Program), and **Audacity which handle 3D movie creation**, 2D image manipulation, and audio editing respectively. They have had various degrees of success in professional markets. Blender is used for everything from independent films to Hollywood movies, for example. GIMP supports high-quality photo manipulation, original artwork creation, graphic design elements, and is extensible through scripting in multiple languages. Audacity is a free and open source audio editing tool that is available on multiple operating systems.
1. **Productivity**: **Use of common open source applications in presentations** and projects is one way to strengthen Linux skills. The basic productivity applications, such as a word processor, spreadsheet, and presentation package are valuable assets. Collectively they’re known as an office suite, primarily due to Microsoft Office, the dominant player in the market. **LibreOffice is a fork of the OpenOffice (**sometimes called OpenOffice.org) application suite. Both offer a full office suite, including tools that strive for compatibility with Microsoft Office in both features and file formats. Shown below is the spreadsheet and the document editor of LibreOffice. Note how the spreadsheet, LibreOffice Calc, is not limited to rows and columns of numbers. The numbers can be the source of a graph, and formulas can be written to calculate values based on information, such as pulling together interest rates and loan amounts to help compare different borrowing options. Using LibreOffice Writer, a document can contain text, graphics, data tables, and much more. You can link documents and spreadsheets together, for example, so that you can summarize data in a written form and know that any changes to the spreadsheet will be reflected in the document.

### 3.3 Console Tools

The development of UNIX shows considerable overlap between the skills of software development and systems administration. The tools for managing systems have features of computer languages such as loops (which allow commands to be carried out repeatedly), and some computer programming languages are used extensively in automating systems administration tasks. Thus, one should consider these skills complementary, and at least a basic familiarity with programming is required for competent systems administrators.

#### 3.3.1 Shells

**At the basic level**, **users interact with a Linux system through a shell whether connecting to the system remotely or from an attached keyboard**. The shell’s job is to accept commands, like file manipulations and starting applications, and to pass those to the Linux kernel for execution. **⁠​​⁠​The Linux shell provides a rich language for iterating over files and customizing the environment**, all without leaving the shell. For example, it is possible to write a single command line that finds files with contents matching a specific pattern, extracts useful information from the file, then copies the new information to a new file.

Linux offers a variety of shells to choose from, mostly differing in how and what can be customized, and the syntax of the built-in scripting language. The two main families are the Bourne shell and the C shell. The **Bourne shell was** named after its creator Stephen Bourne of Bell Labs. The **C shell was** so named because its syntax borrows heavily from the C language. As both these shells were invented in the 1970s, there are more modern versions, the Bourne Again Shell (Bash) and the tcsh (pronounced as tee-cee-shell). Bash is the default shell on most systems, though tcsh is also typically available.

Programmers have taken favorite features from Bash and tcsh and made other shells, such as the Korn shell (ksh) and the **Z shell (zsh)**. The choice of shells is mostly a personal one; users who are comfortable with Bash can operate effectively on most Linux systems. Other shells may offer features that increase productivity in specific use cases.

#### 3.3.2

Most Linux systems provide a choice of text editors which are commonly used at the console to edit configuration files. The two main applications are Vi (or the more modern Vim) and Emacs. Both are remarkably powerful tools to edit text files; they differ in the format of the commands and how plugins are written for them. Plugins can be anything from syntax highlighting of software projects to integrated calendars.

Both Vi and Emacs are complex and have a steep learning curve, which is not helpful for simple editing of a small text file. Therefore, Pico and Nano are available on most systems and provide very basic text editing.

**Consider This**: The Nano editor was developed as a completely open source editor that is loosely based on Pico, as the license for Pico is not an open source license and forbids making changes and distributing it.

While Nano is simple and easy to use, it doesn’t offer the extensive suite of more advanced editing and key binding features that an editor like Vi does. Administrators should strive to gain some basic familiarity with Vi, though, because it is available on almost every Linux system in existence. When restoring a broken Linux system by running in the distribution’s recovery mode, Vi can be a critical tool, and the best time to learn Vim or any editor is before you desperately need it to fix a broken system.

### 3.4

Every Linux system needs to add, remove, and update software. In the past this meant downloading the source code, setting it up, compiling it, and copying files onto each system that required updating. Thankfully, **modern distributions use packages**, **which are compressed files that bundle up an application and its dependencies** (or required files), greatly simplifying the installation by making the right directories, copying the proper files into them, and creating such needed items as symbolic links.

A package manager takes care of keeping track of which files belong to which package and even downloading updates from repositories, typically a remote server sharing out the appropriate updates for a distribution. In Linux, there are many different software package management systems, but **the two most popular are those from Debian and Red Hat**.

#### 3.4.1 Debian Package Management

The Debian distribution, **and its derivatives such as Ubuntu and Mint**, use the Debian package management system. At the heart of Debian package management are software packages that are distributed as files **ending in the .deb extension**.

The lowest-level tool for managing these files is the **dpkg command**. This command can be tricky for novice Linux users, so the **Advanced Package Tool**, **apt-get** (**a front-end program to the dpkg tool**), **makes management of packages easier**. Additional command line tools which serve as front-ends to dpkg include aptitude and GUI front-ends like Synaptic and Software Center.

#### 3.4.2 RPM Package Management

The Linux Standards Base, which is a Linux Foundation project, is designed to specify (through a consensus) **a set of standards that increase the compatibility between conforming Linux systems**. According to the **Linux Standards Base**, **the standard package management system is RPM**.

**RPM makes use of an .rpm file for each software package**. This system is what distributions derived **from Red Hat, including Centos and Fedora, use to manage software**. **Several other distributions that are not Red Hat derived, such as SUSE, OpenSUSE, and Arch, also use RPM**.

**Like the Debian system, RPM Package Management systems track dependencies between packages**. **Tracking dependencies ensures that when a package is installed, the system also installs any packages needed by that package to function correctly**. Dependencies also ensure that software updates and removals are performed properly.

The back-end tool most commonly used for **RPM Package Management is the rpm command**. **While the rpm command can install, update, query and remove packages, the command line front-end tools such as yum and up2date automate the process of resolving dependency issues**.

Note

A back-end program or application either interacts directly with a front-end program or is "called" by an intermediate program. Back end programs would not interact directly with the user. Basically, there are programs that interact with people (front-end) and programs that interact with other programs (back-end).

There are also GUI-based front-end tools such as Yumex and Gnome PackageKit that also make RPM package management easier.

Some RPM-based distributions have implemented the ZYpp (or libzypp) package management style, mostly openSUSE and SUSE Linux Enterprise, but mobile distributions MeeGo, Tizen and Sailfish as well.

The zypper command is the basis of the ZYpp method, and it features short and long English commands to perform functions, such as zypper in packagename which installs a package including any needed dependencies.

Most of the commands associated with package management require root privileges. The rule of thumb is that if a command affects the state of a package, administrative access is required. In other words, a regular user can perform a query or a search, but to add, update or remove a package requires the command to be executed as the root user.

### 3.5 Development Languages

It should come as no surprise that as software built on contributions from programmers, Linux **has excellent support for software development**. The shells are built to be programmable, and there are powerful editors included on every system. There are also many development tools available, and many modern programming languages treat Linux as a first-class citizen.

Computer programming languages provide a way for a programmer to enter instructions in a more human readable format, and for those instructions to eventually become translated into something the computer understands. Languages fall into one of two camps: interpreted or compiled. An interpreted language translates the written code into computer code as the program runs, and a compiled language is translated all at once.

**Linux itself was written in a compiled language called C**. **The main benefit of C is that the language itself maps closely to the generated machine code so that a skilled programmer can write code that is small and efficient**. When computer memory was measured in kilobytes, this was very important. Even with large memory sizes today, **C is still helpful for writing code that must run fast, such as an operating system**.

**C has been extended over the years. There is C++, which adds object support to C (a different style of programming), and Objective C that took another direction and is in heavy use in Apple products.**

The Java language puts a different spin on the compiled approach. **Instead of compiling to machine code, Java first imagines a hypothetical CPU called the Java Virtual Machine (JVM) and then compiles all the code to that**. **Each host computer then runs JVM software to translate the JVM instructions (called bytecode) into native instructions**.

The additional translation with Java might make you think it would be slow. However, the JVM is relatively simple so it can be implemented quickly and reliably on anything from a powerful computer to a low power device that connects to a television. A compiled Java file can also be run on any computer implementing the JVM!

Another benefit of compiling to an intermediate target is that the JVM can provide services to the application that usually wouldn’t be available on a CPU. Allocating memory to a program is a complex problem, but it’s built into the JVM. As a result, JVM makers can focus their improvements on the JVM as a whole, so any progress they make is instantly available to applications.

**Interpreted languages, on the other hand, are translated to machine code as they execute**. The extra computer power spent doing this can often be recouped by the increased productivity the programmer gains by not having to stop working to compile. **Interpreted languages also tend to offer more features than compiled languages, meaning that often less code is needed**. The language interpreter itself is usually written in another language such as C, and sometimes even Java! This means that an interpreted language is being run on the JVM, which is translated at runtime into actual machine code.

**JavaScript is a high-level interpreted programming language that is one of the core technologies on the world wide web**. It is similar to but fundamentally different from Java, which is a completely object-oriented programming language owned by Oracle. **JavaScript is a cross-platform scripting language for adding interactive elements to web pages, that is in wide use across the internet**. By using **JavaScript libraries, web programmers can add everything from simple animations to complex server-side applications for internet users**. **JavaScript is continuously evolving to meet the functionality and security needs of internet users and is capable of being released under a GNU GPL License**.

**Consider This**: The term object-oriented refers to programing that abstracts complex actions and processes so that the end user only deals with basic tasks. To visualize this concept, think of a machine that performs a complex set of tasks by simply pushing a button.

**Perl is an interpreted language**. Perl was originally developed to perform text manipulation. Over the years, it gained favor with systems administrators and continues to be improved and used in everything from automation to building web applications.

**PHP is a language that was** initially built to create dynamic web pages. A PHP file is read by a web server such as Apache. Special tags in the file indicate that parts of the code should be interpreted as instructions. The web server pulls all the different parts of the file together and sends it to the web browser. PHP’s main advantages are that it is easy to learn and available on almost any system. Because of this, many popular projects are built on PHP. Notable examples include WordPress (for blogging), cacti (for monitoring), and even parts of Facebook.

**Ruby is another language that was influenced by Perl and Shell**, along with many other languages. It makes complex programming tasks relatively easy, and with the inclusion of the Ruby on Rails framework, is a popular choice for building complex web applications. Ruby is also the language that powers many of the leading automation tools like Chef and Puppet, which make managing a large number of Linux systems much simpler.

**Python is another scripting language **that is in general use. Much like Ruby it makes complex tasks easier and has a framework called Django that makes building web applications very easy. Python has excellent statistical processing abilities and is a favorite in academia.

A computer programming language is just a tool that makes it easier to tell the computer what you want it to do. A library bundles common tasks into a distinct package that can be used by the developer. ImageMagick is one such library that lets programmers manipulate images in code. ImageMagick also ships with some command line tools that enable programmers to process images from a shell and take advantage of the scripting capabilities there.

OpenSSL is a cryptographic library that is used in everything from web servers to the command line. It provides a standard interface for adding cryptography into a Perl script, for example.

At a much lower level is the C library. The C library provides a basic set of functions for reading and writing to files and displays, and is used by applications and other languages alike.

### 3.6 Security

Administrators and computer users are increasingly aware of privacy concerns in both their personal and professional lives. High-profile data breaches have been in the news all too often recently, and the cost of these break-ins can reach into the millions of dollars for the institutions that fall victim to hackers and ransomware attacks. Many times the cause of these breaches is simply human error such as opening a suspicious email or entering passwords into a phony login page.

**Cookies are the primary mechanism that websites use to track you**. Sometimes this tracking is good, such as to keep track of what is in your shopping cart or to keep you logged in when you return to the site.

As you browse the web, a web server can send back the cookie, which is a small piece of text, along with the web page. **Your browser stores this information and sends it back with every request to the same site.** Cookies are normally only sent back to the site they originated from, so a cookie from example.com wouldn’t be sent to example.org.

However, many sites have embedded scripts that come from third parties, such as a banner advertisement or Google analytics pixel. If both example.com and example.org have a tracking pixel, such as one from an advertiser, then that same cookie will be sent when browsing both sites. The advertiser then knows that you have visited both example.com and example.org.

With a broad enough reach, such as placement on social network sites with “Like” buttons and such, a website can gain an understanding of which websites you frequent and figure out your interests and demographics.

There are various strategies for dealing with this. One is to ignore it. The other is to limit the tracking pixels you accept, either by blocking them entirely or clearing them out periodically.

Browsers typically offer cookie-related settings; users can opt to have the browser tell the site not to track. This voluntary tag is sent in the request, and some sites will honor it. The browser can also be set never to remember third-party cookies and remove regular cookies (such as from the site you are browsing) after being closed.

Tweaking privacy settings can make you more anonymous on the Internet, but it can also cause problems with some sites that depend on third-party cookies. If this happens, you might have to explicitly permit some cookies to be saved.

#### 3.6.1 Password issues

**Good password management is essential to security in any computing environment**. The Linux systems administrator is often the person responsible for setting and enforcing password policies for users at all levels. **The most privileged user on any Linux system is root**; this account **is the primary administrator and is created when the operating system is installed**. Often administrators will disable root access as the first line of defense against intrusion since computer hackers will try to gain root access in order to take control of the system.

There are many levels of access and various means of password management on a Linux system. **When users are created, they are given different login permissions depending on what groups they are assigned to.** For example, administrators can create and manage users while regular users cannot. Services that run on systems such as databases can also have login permissions with their own passwords and privileges. Additionally, there are specific passwords for accessing systems remotely through SSH, FTP, or other management programs.

Managing all these accounts, and their accompanying passwords is a complicated and necessary part of the systems administrator role. Passwords need to be complex enough not to be easily guessed by hackers, yet easy to remember for users. Increasingly users and administrators are turning to password manager programs to store login credentials in encrypted form. Another trend is two-factor authentication (2FA), a technique where a password is supplemented by a second “factor,” often a passcode sent to the user's phone or other devices. Keeping up with current security trends, while ensuring authorized users' ease of access, is an ongoing challenge that must be met.

#### 3.6.2 Protecting Yourself

As you browse the web, you leave a digital footprint. Much of this information goes ignored; some of it is gathered to collect statistics for advertising, and some can be used for malicious purposes.

The easiest thing you can do is to use a good, unique password everywhere you go, especially on your local machine. A good password is at least 10 characters long and contains a mixture of numbers, letters (both upper and lower case) and special symbols. Use a password manager like KeePassX to generate passwords, and then you only need to have a login password to your machine and a password to open up your KeePassX file.

Also, limit the information you give to sites to only what is needed. While giving your mother’s maiden name and birthdate might help unlock your social network login if you lose your password, the same information can be used to impersonate you to your bank.

After that, make a point of checking for updates periodically. The system can be configured to check for updates on a regular basis. If there are security-related updates, you may be prompted immediately to install them.

#### 3.6.3 Privacy Tools

The use of modern privacy tools, both at the server and user level, can help prevent system intrusions and unauthorized access to data.

The good news is that Linux is by default one of the most secure operating systems ever created. Many of the exploits that plague other operating systems simply won’t work on Linux due to the underlying architecture. However, there are still many known weaknesses that hackers can take advantage of so the proactive systems administrator is wise to deploy privacy tools that protect their users as well as the systems they use.

Encryption is probably the best-known and most widely-deployed privacy tool in use today. Administrators deploy encryption with authentication keys on almost every system that communicates with the outside world. One well-known example is the HyperText Transfer Protocol Secure (HTTPS) standard used on web servers to ensure that data transmitted between users and online resources cannot be intercepted as it travels on the open Internet.

Virtual private networks (VPN) have been in use by companies to connect their remote servers and employees for many years. Now they are gaining popularity amongst ordinary users looking to protect their privacy online. They work by creating an encrypted channel of communication between two systems, so the data transmitted between them is scrambled by an algorithm only the systems know.

The Tor project has long been involved in creating privacy tools like it’s Tor Browser that works by relaying internet requests through a network of servers that prevents websites and others from learning the identity of the person making the request.

These tools are constantly evolving and choosing which ones are appropriate for the users and systems involved is an essential part of the systems administrator's role.

### 3.7 The Cloud

**Organizations are increasingly looking at the cloud as essential to their businesses and operations**. The migration of an organization's IT applications and processes to cloud services, known as cloud adoption, is rapidly becoming a strategic business decision for many.  Cloud computing **is seen as one of the major disruptive technologies of the coming decade which will significantly transform businesses, economies, and lives globally**.

**Physically**, a cloud can be described as computing resources from one or many off-site data centers which can be accessed over the internet. **The cloud builds on the benefits of a data center and provides computing solutions to organizations who need to store and process data, and it allows them to delegate management of IT infrastructure to a third-party.** **The data and resources that organizations store in the cloud can include data, servers, storage, application hosting, analytics and a myriad of other services**.

A cloud deployment model provides a basis for how cloud infrastructure is built, managed, and accessed. There are four primary cloud deployment models:
* **Public Cloud**: A public cloud is a cloud infrastructure deployed by a provider to offer cloud services to the general public and organizations over the Internet. In the public cloud model, there may be multiple tenants (consumers) who share common cloud resources. More than likely, many of us have accessed public cloud resources at some point through providers such as Amazon, Google, and other popular public cloud providers.
* **Private Cloud**: A private cloud is a cloud infrastructure that is set up for the sole use of a particular organization. When compared to a public cloud, a private cloud offers organizations a greater degree of privacy, and control over the cloud infrastructure, applications, and data. It can be hosted either on servers managed by the company that is using it or through a managed private cloud provider such as Rackspace or IBM.
* **Community Cloud**: A community cloud is a cloud infrastructure that is set up for the sole use by a group of organizations with common goals or requirements. The organizations participating in the community typically share the cost of the community cloud service. This option may be more expensive than the public cloud; however, it may offer a higher level of control and protection against external threats than a public cloud.
* **Hybrid Cloud**: A hybrid cloud is composed of two or more individual clouds, each of which can be a private, community, or public cloud. A hybrid cloud may change over time as component clouds join and leave. The use of such technology enables data and application portability. It also allows companies to leverage outside resources while retaining control of sensitive resources.

#### 3.7.1 Linux in the Cloud

**Linux plays a pivotal role in cloud computing**. **It powers 90% of the public cloud workload, most virtual servers are based on some version of the Linux kernel, and Linux is often used to host the applications behind cloud computing services. So what makes Linux uniquely suited to enabling cloud computing?**

* **Flexibility**: Cloud computing provides the capability to provision IT resources quickly and at any time. This agility enables rapid development and experimentation that, in turn, facilitates innovation which is essential for research and development, the discovery of new markets and revenue opportunities, creating new customer segments, and the development of new products. As a result, cloud computing must compensate for the fact that each organization has a unique, evolving set of resource requirements. **Linux stands out here because it is highly adaptable**. For starters, **Linux is modular by design, and at the center of an enormous ecosystem of open source applications providing endless configuration options to suit various systems and use cases**. On top of that, **Linux scales efficiently, allowing it to run anything from a tiny remote sensor to an entire server farm**.

* **Accessibility**: In a traditional environment, IT resources are accessed from dedicated devices, such as a desktop or a laptop. In cloud computing, applications and data reside centrally and are accessed from anywhere over a network from any device, such as desktop, mobile, or thin client, and there is a version of Linux for every single one of these devices.

* **Cost-Effective**: Cloud computing is attractive as it has the potential for consumers to reduce their IT costs. In cloud computing, consumers can unilaterally and automatically scale IT resources to meet workload demand, thereby eliminating overhead from underutilized resources. Additionally, the expenses associated with IT configuration, management, floor space, power, and cooling are reduced. Cloud providers absorb these infrastructure costs but must remain a low-cost alternative. Choosing Linux is one of the most cost-effective solutions providers can deploy. Linux is one of the most power efficient operating systems, and the Linux kernel is completely free, as are many associated applications, utilities, and additional software components. Enterprise and government organizations can opt to pay for commercially-supported distributions, which are still more cost-effective when compared to licensed competitors. Non-commercial distributions that support cloud computing also are a viable option for many organizations. Not only can vendors pass these savings onto the customers, offering Linux-based solutions can be cheaper for the client to implement. Setting up Linux on their own systems eliminates expensive user licensing fees potentially associated with competing operating systems.

* **Manageability**: While Linux began as a niche operating system, its widespread presence in the IT industry has made Linux use and administration a necessary skill for IT professionals. It is becoming increasingly easy for cloud vendors and consumers to acquire the necessary talent, or reallocate existing team members. The nature of Linux, built on the C programming language, also lends itself to automated management tools. A significant portion of Linux servers operating in the cloud are created and managed by automated management programs rather than human operators. This process frees up administrators to monitor computing operations rather than manually configuring and updating systems.

* **Security**: When using a cloud solution, especially a public cloud, **an organization may have concerns related to privacy, external threats, and lack of control over the IT resources and data**. Linux can help offset these issues because it is one of the most secure and reliable operating systems available. **Linux is open source, meaning its source code is available for anyone to obtain, review, and modify**. This also means the code can be inspected for vulnerabilities and compatibility issues, resulting in an extensive community effort to rectify these issues and uphold the robust reputation of Linux.

* **Virtualization**: **Virtualization is one of the most significant advancements that has contributed to the enablement cloud of computing.** **Linux is a multi-user operating system**, which means that **many different users can work on the same system simultaneously and for the most part can’t do things to harm other users**. However, this does have limitations – **users can hog disk space or take up too much memory or CPU resources and make the system slow for everyone.** Sharing the system in multi-user mode also requires that everyone run as unprivileged users, so letting each user run their own web server, for example, is challenging. **Virtualization is the process where one physical computer, called the host, runs multiple copies of an operating system, each copy called a guest.** These guest images can be pre-configured for specific functions to allow rapid deployment, often automatically, when needed. **The host system runs software called a hypervisor that switches resources between the various guests just like the Linux kernel does for individual processes**. **With bare metal hypervisors, the hypervisor runs directly on computer hardware rather than on top of an OS freeing up more resources for guest images.** **Virtualization works because servers spend most of their time idling and don’t need physical resources such as a monitor and keyboard.** With software from companies like VMWare and Openbox, you can now take a powerful CPU and by using it to run multiple virtual machines administrators can optimize usage of physical resources and dramatically reduce costs over the previous one-machine, one-OS data center model. **The main limitation is usually memory, however, with advances in hypervisor technology and CPUs, it is possible to put more virtual machines on one host than ever.** In a virtualized environment one host can run dozens of guest operating systems, and with support from the CPU itself, the guests don’t even know they are running on a virtual machine. Each guest gets its own virtual resources and communicates with the network on its own. It is not even necessary to run the same operating system on all the guests, which further reduces the number of physical servers needed. Virtualization offers a way for an enterprise to lower power usage and reduce data center space over an equivalent fleet of physical servers. Guests are now just software configurations, so it is easy to spin up a new machine for testing and destroy it when its usefulness has passed. Since it is possible to run multiple instances of an operating system on one physical machine and connect to it over the network, the location of the machine doesn’t matter. Cloud computing takes this approach and allows administrators to have virtual machines in a remote data center owned by another company, and only pay for the resources used. Cloud computing vendors can take advantage of scales of economy to offer computing resources at far lower prices than operating an on-site data center.

* **Containers and Bare Metal Deployments**: **With the rise of containerization technologies like Docker and Kubernetes application software is now being written that runs in a serverless environment.** Essentially, **programmers are creating software that does one single function of a system (like database processing or storage) that runs in a container.** **These containers are organized in pods that run within a node and can talk with each other, and the outside world if needed.** **Nodes, in turn, are organized and controlled by a master node that provides services to each component within the structure.** **Building applications in this way decouples each of the components from the others, and from the overhead of running an OS.** Since each piece of the puzzle can be automatically destroyed and recreated by the master node they no longer need to be as robust as software that runs on top of an OS. **Although these new programming architectures are in many ways bypassing the need for a traditional OS the underlying technology that makes them work is still Linux**. So, **working in Linux will increasingly be working within a development team that draws on the disciplines of programming, database design, networking, and systems administration to create the systems of the future**. 

### Key terms

* Apache HTTPD: Apache HTTPD is a server application program, or daemon, that manages web page requests on an Apache web server. Section 3.2.2.1 
* C: A compiled computer programming language. C is the language in which Linux is written.    Section 3.5 
* Firefox: An open source, cross-platform web browser developed by the Mozilla Foundation.     Section 3.2.3.4 
* GIMP: An open source application which handles 2D image manipulation. Section 3.2.3.2 
* Java: A compiled, object-oriented programming language owned by Oracle. Section 3.5 
* JavaScript: A cross-platform scripting language for adding interactive elements to web pages, that is in wide use across the internet. Section 3.5 
* LibreOffice: An open source office suite forked from Open Office. It includes tools that strive for compatibility with Microsoft Office in both features and file formats. Section 3.2.3.3 
* MariaDB: An open source database application forked from MySQL. It records data written to it by dynamic web applications. Section 3.2.2.3 
* MySQL: A relational database management system used for web development. Section 3.2.2.3 
* NFS: The native file sharing protocol for Unix and Linux. Short for Network File System.     Section 3.2.2.5 
* NGINX: An open source web server based out of Russia focused on the use of more modern UNIX kernels. Section 3.2.2.1 
* Nextcloud: An open source private cloud server software forked from ownCloud. It is provided under a GNU AGPLv3 that can be deployed and administered internally by an organization.    Section 3.2.2.2 
* OpenOffice.org: An open source office suite which has been discontinued. Section 3.2.3.3 
* PHP: A scripting language designed to create dynamic web pages. Section 3.5 
* Perl: An interpreted programming language popular with system adminsitrators. It was orginally developed to perform text manipulation. Section 3.5 
* Python: A scripting language which simplifies complex tasks, has excellent statistical processing, and it popular in academia. Section 3.5 
* Samba: A file sharing application ideal for use with Windows systems. Section 3.2.2.5 
* Thunderbird: A full-featured, open source desktop email client developed by the Mozilla Foundation. Section 3.2.3.1 
* apt-get: A front-end program for Debian package management. Section 3.4.1 
* console: Traditionally used to refer to a physical terminal. Section 3.1.1 
* dpkg: The package management system used on Debian derived Linux distributions. Section 3.4.1 
* ownCloud: An open source file hosting service. The project was launched in 2010 by Frank Karlitschek to provide software to store, sync and share data from private cloud servers.    Section 3.2.2.2 
* password issues: Section 3.6.1 
* privacy issues and tools: Section 3.6.2 
* rpm: The package management system used on Red Hat derived Linux distributions. According to the Linux Standards Base, the standard package management system is RPM. Section 3.4.2 
* shell: The user interface of a Linux system. It interacts with the user by accepting commands, passes them to the kernel for execution, and displays any output to the terminal. Section 3.3.1 
* terminal: The environment or device in which the user interacts with the software. It can also refer to a graphical program which emulates a console. Section 3.1.1 
* use of common open source applications in presentations and projects: Section 3.2.3.3 
* using a browser, privacy concerns, configuration options, searching the web and saving content: Section 3.6.2 
* yum: A front-end tool for RPM package management. Section 3.4.2 

