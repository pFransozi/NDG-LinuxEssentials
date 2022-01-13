# NDG Linux Essentials

## Chapter 2

1.1 : Linux Evolution and Popular Operating Systems
Weight: 2
Knowledge of Linux development and major distributions.

* Key Knowledge Areas:
    * Distributions: Section 2.4
    * Embedded Systems: Section 2.4.2

4.1: Choosing an Operating System
Weight: 1
Knowledge of major operating systems and Linux distributions.

*Key Knowledge Areas:
    * Differences between Windows, OS X and Linux: Section 2.2 | Section 2.3 | Section 2.4
    * GUI versus command line: Section 2.4
    * Distribution life cycle management: Section 2.4


### 2.1 Operating Systems

* OS is software that **runs on a computing device** and **manages the hardware and software components that make up a functional computing system**, even though modern OS **don’t just manage hardware and software resources**, **they schedule programs to run in a multi-tasking manner** **(sharing the processor so that multiple tasks can occur apparently simultaneously)**, **provide standard services** that allow users and programs to request something happen (for example **a print job**) from the operating system, and provided it’s properly requested, the operating system will accept the request and perform the function needed.

* Computer users today have a choice mainly between three major operating systems: Microsoft Windows, Apple macOS, and Linux.

### 2.1.1. Decision Points

* **role**: will you be sitting at the console running productivity applications or web browsing? If so, a familiar **desktop is best**. Will the machine be accessed remotely by many users or provide services to remote users? Then **it’s a server**.

* **function**: Is there specific software it needs to run, or specific functions it needs to perform? Will there be hundreds, even thousands, of these machines running at the same time? What is the skill-set of the team managing the computer and software?

* **life cycle**: **service lifetime and risk tolerance of the server also needs to be determined**. OS and software upgrades come on a periodic basis, called a release cycle. Vendors only support older versions of software **for a certain period of time before not offering any updates**; this is called a maintenance cycle or life cycle. In an enterprise server environment, **maintenance and release cycles are critical considerations because it is time-consuming and expensive to do major upgrades**. Instead, the server hardware itself is often replaced because increased performance is worth the extra expense, and the resources involved are often many times more costly than the hardware.

**Consider This**: There is a fair amount of work involved in upgrading a server due to specialized configurations, application software patching and user testing, **so a proactive organization will seek to maximize their return on investment in both human and monetary capital**. Modern data centers **are addressing this challenge through virtualization**. In a virtual environment, one physical machine can host dozens, or even hundreds of virtual machines, decreasing space and power requirements, as well as providing for automation of many of the tasks previously done manually by systems administrators. Scripting programs allow virtual machines to be created, configured, deployed and removed from a network without the need for human intervention. Of course, a human still needs to write the script and monitor these systems, at least for now. **The need for physical hardware upgrades has also been decreased immensely with the advent of cloud services providers like Amazon Web Services, Rackspace, and Microsoft Azure**. Similar advances have helped desktop administrators manage upgrades in an automated fashion and with little to no user interruption.

* **stability**: individual software releases can be characterized as beta or stable depending on where they are in the release cycle. When a software release has many new features that haven’t been tested, it’s typically referred to as beta. After being tested in the field, its designation changes to stable. **Users who need the latest features can decide to use beta software. This is often done in the development phase of a new deployment and provides the ability to request features not available on the stable release.** **Production servers typically use stable software unless needed features are not available, and the risk of running code that has not been thoroughly tested is outweighed by the utility provided.** Software in the **open source realm is often released for peer review very early on in its development process, and can very quickly be put into testing and even production environments**, **providing extremely useful feedback and code submissions to fix issues found or features needed**.

* **compatibility**: another **loosely-related concept is backward compatibility** which refers to the ability of later operating systems to be compatible with software made for earlier versions. **The norm for open source software development is to ensure backward compatibility first and break things only as a last resort**. The common practice of maintaining and versioning libraries of functions helps this greatly. Typically, a library that is used by one or more programs is versioned as a new release when significant changes have occurred but also keeps all the functions (and compatibility) of earlier versions that may be hard-coded or referred to by existing software.

* **cost**: Cost is always a factor when specifying new systems. Virtualization and outsourced support services offer the modern IT organization **the promise of having to pay for only what it uses rather than building in excess capacity**. This not only controls costs but offers opportunities for people both inside and outside the organization to provide expertise and value.

* **interface**: OSs offer both GUI and CLI interfaces, however, most consumer operating systems (Windows, macOS) are designed to shield the user from the ins and outs of the CLI.

### 2.2 Microsoft Windows

* Microsoft offers different versions of its operating system according to the machine’s role: desktop or server? The desktop version of Windows has undergone various naming schemes with the current version (as of this writing) being simply Windows 11. While new versions of most Linux distributions come out twice a year, around March and September, new versions of Windows tend to be released only every few years. In all, there have been 16 versions of Windows since 1985. Backward compatibility is a priority for Microsoft, even going so far as to bundle virtual machine technology so that users can run older software.

* Windows Server currently (as of this writing) is at version 2019 to denote the release date. The server can run a GUI but recently Microsoft, largely as a competitive response to Linux, **has made incredible strides in its command line scripting capabilities through PowerShell and Windows Subsystem for Linux (WSL, https://docs.microsoft.com/pt-br/windows/wsl/about)**. There is also an optional Desktop Experience package which mimics a standard productivity machine. Microsoft also actively encourages enterprise customers to incorporate its Azure cloud service.

### 2.3 Apple macOS

* Apple makes the macOS operating system, which is partially based on software from the FreeBSD project and has undergone UNIX certification. macOS is well known for being “easy to use”, and as such has continued to be favored by users with limited access to IT resources like schools and small businesses. It is also very popular with programmers due to its robust UNIX underpinnings.

On the server side, macOS Server is primarily aimed at smaller organizations. This low-cost addition to macOS desktop allows users to collaborate, and administrators to control access to shared resources. It also provides integration with iOS devices like the iPhone and iPad.

Some large corporate IT departments allow users to choose macOS since users often require less support than standard Microsoft productivity deployments. The continued popularity of macOS has ensured healthy support from software vendors. macOS is also quite popular in the creative industries such as graphics and video production. For many of these users, application choice drives the operating system decision. Apple hardware, being integrated so closely with the operating system, and their insistence on adherence to standards in application programming gives these creative professionals a stable platform to perform many computing-intense functions with fewer concerns about compatibility.

### 2.4 Linux

* A Linux distribution is a bundle of software, typically comprised of the Linux kernel, utilities, management tools, and even some application software in a package which also includes the means to update core software and install additional applications.

* The distribution takes care of setting up the storage, building the kernel and installing hardware drivers, as well as installing applications and utilities to make a fully functional computer system. The organizations that create distributions also include tools to manage the system, a package manager to add and remove software, as well as update programs to provide security and functionality patches.

* **role**: the variety of distributions and accompanying software **allows the OS to be significantly more flexible and customizable**.

* **function**: Different distributions have different versions of key libraries, and it is difficult for a company to support all these different versions. However, some applications like Firefox and LibreOffice are widely supported and available for all major distributions. Governments and large enterprises may also limit their choices to distributions that offer commercial support because paying for another tier of support may be better than risking extensive outages. For the most part, concerns over security have been addressed through the large open source community, which monitors kernel changes for vulnerabilities and provides bug reporting and fixes at a much larger scale than closed source vendors can achieve. 

* **life cycle**: Most distributions have both major and minor update cycles to introduce new features and fix existing bugs. Linux distributions can be broadly classed in two main categories: enthusiast and enterprise. An enthusiast distribution such as openSUSE’s Tumbleweed has a fast update cycle, is not supported for enterprise and may not contain (or drop) features or software in the next version that are in the current one. Red Hat’s Fedora project uses a similar method of development and release cycle, as does Ubuntu Desktop. Enterprise distributions are almost the exact opposite, in that they take care to be stable and consistent, and offer enterprise-grade support for extended periods, anywhere from 5-13 years in the case of SUSE. Enterprise distributions are fewer by far, being offered mainly by Red Hat, Canonical and SUSE.  some Linux releases are considered to have long-term support (LTS) of 5 years or more while others are only supported for two years or less.

* **stability**: Some distributions offer stable, testing, and unstable releases.

* **cost**: Your chosen Linux distribution itself might be zero cost, but paying for support may be worthwhile depending on organizational needs and capabilities.

* **interface**: graphical (GUI) and non-graphical (CLI)

### 2.4.1 Linux Distributions

* **red hat**: it started as a simple distribution **that introduced the Red Hat Package Manager (RPM)**. Red Hat started **to focus more on the server applications**, such as web- and file-serving and released **Red Hat Enterprise Linux (RHEL)**, **which was a paid service on a long release cycle**. Red Hat sponsors the **Fedora Project** which makes a personal desktop comprising the latest software but is still built on the same foundations as the enterprise version. **Because everything in Red Hat Enterprise Linux is open source**, **a project called CentOS came to be**. It recompiled all the RHEL packages (converting their source code from the programming language they were written into language usable by the system) and gave them away for free. **CentOS and others like it** (such as Scientific Linux) **are largely compatible with RHEL and integrate some newer software, but do not offer the paid support that Red Hat does**. **Scientific Linux** is an example of a specific-use distribution based on Red Hat. **The project is a Fermilab-sponsored distribution designed to enable scientific computing**. Among its many applications, Scientific Linux is used with particle accelerators including the Large Hadron Collider at CERN.

* **suse**: SUSE, originally **derived from Slackware**, was **one of the first comprehensive Linux distributions**, it has **many similarities to Red Hat Enterprise Linux**. **While SUSE Linux Enterprise contains proprietary code and is sold as a server product, openSUSE is a completely open, free version with multiple desktop packages similar to CentOS and Linux Mint.**

* **debian**: Debian is more of a community effort, and as such, also promotes the use of open source software and adherence to standards. Debian came up with its own package management system **based on the .deb file format**. **Ubuntu is the most popular Debian-derived distribution**. It is the creation of Canonical, a company that was made to further the growth of Ubuntu and makes money by providing support. Ubuntu has several different variants for desktop, server and various specialized applications. They also offer an LTS version that is kept up-to-date for 3 years on desktops and 5 years on servers, which gives developers and the companies they work for confidence to build solutions based on a stable distribution. ‌⁠⁠Linux Mint was started as a fork of Ubuntu Linux, while still relying upon the Ubuntu repositories. There are various versions, all free of cost, but some include proprietary codecs, which cannot be distributed without license restrictions in certain countries.

* **android**: Android, sponsored by Google, is the world’s most popular Linux distribution. It is fundamentally different from its counterparts. Android uses the Dalvik virtual machine with Linux, providing a robust platform for mobile devices such as phones and tablets. However, lacking the traditional packages that are often distributed with Linux (such as GNU and Xorg), Android is generally incompatible with desktop Linux distributions.

* **other**: Linux From Scratch (LFS) is more of a learning tool than a working distribution. This project consists of an online book, and source code, with “step-by-step instructions” for building a custom Linux distribution from the source code up.

### 2.4.2 Embedded systems


* **Because of this flexibility**, a significant number of device makers have used Linux as the operating system for their hardware products. Today we call these embedded systems because they are designed to do a specific task on hardware optimized for only that purpose. These systems encompass a tremendous diversity of devices that are used today, from cell phones to smart TVs and appliances, to remote monitoring systems for pipelines and factories.

* As Linux evolved, specialized processor chips were developed for consumer and industrial devices to take advantage of its capabilities. Support for Linux has become so ubiquitous that it is possible to prototype and bring to market new devices using off-the-shelf components. The rise of cheap, small, adaptable single-board computers like the Raspberry Pi has given experimenters and entrepreneurs everywhere tools to quickly build custom solutions, powered by Linux, that would have taken months of work by specialized teams just a few years ago.


### Key Terms

* Android: A Linux distribution that provides a platform for mobile users but lacks the traditional GNU/Linux packages to make it compatible with desktop Linux distributions. Section 2.4.1 
* CentOS: A Linux distribution that is compatible with Red Hat Enterprise Linux but does not offer the paid support that Red Hat does. Section 2.4.1 
* Debian: An operating system that uses the Linux kernel. It that promotes the use of open source software and adherence to standards. Section 2.4.1 
* Linux Mint: A Linux distribution that is a derivative of Ubuntu and still relies upon the Ubuntu repositories. Section 2.4.1
* Raspberry Pi: A hardware platform used in training for programmers and hardware designers at all levels. Its low cost and ease of use have made it popular with educators. Section 2.4.1
* Raspbian: A specialized Linux distribution optimized to run on Raspberry Pi hardware. Section 2.4.1 
* Red Hat: A Linux distribution that introduced Red Hat Package Manager (RPM). The developer formed a company by the same name which specializes in open source software. Section 2.4.1 
* SUSE: One of the first comprehensive Linux distributions. It is derived from Slackware which offers many similarities with Red Hat Enterprise Linux. Section 2.4.1 
* Scientific Linux: A specific use distribution based on Red Hat. It was designed to enable scientific computing. Section 2.4.1 
* Ubuntu: The most popular Debian derived distribution. It has several different variants for desktop, server, and various specialized applications as well as an LTS version. Section 2.4.1 
* beta: A software release that has many new features that haven’t been tested. Section 2.1.1 
* command line interface (CLI):  A text based interface in which the user enters commands. Feedback, output and programs are presented in text format only. Section 2.1.1 
* desktop configuration: Desktop are preferred if the user interacts with the system directly. Desktop system primarily run a GUI for the ease of use of its user.2.1.1 Section 2.1.1 
* graphical user interface (GUI): A visual user interface that allows the user to interact with the system using windows, icons, a cursor, etc. Section 2.1.1 
* long-term support (LTS): Associated with the life cycle of distributions, this feature states that software is supported for 5 years or more. Section 2.4 
* maintenance cycles: The period of time vendors support older versions of software before not offering any updates. Section 2.1.1 
* openSUSE: A Linux distribution that is a completely open, free version of SUSE Linux Enterprise with multiple desktop packages similar to CentOS and Linux Mint. Section 2.4.1 
* stable: A software release whose updates have been tested in the field. Section 2.1.1 

