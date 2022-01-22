# NDG Linux Essentials

## Chapter 4

This chapter will cover the following exam objectives: 1.3: Open Source Software and Licensing

Weight: 1

Open communities and licensing Open Source Software for business.

Key Knowledge Areas:

* Open Source Initiative (OSI): Section 4.2.2
* Open source licensing: Section 4.2
* Open source philosophy: Section 4.1
* Free Software Foundation (FSF): Section 4.2.1

### 4.1 Introduction

Software projects take the form of source code, which is a human-readable set of computer instructions. Since source code is not understood directly by the computer, it must be compiled into machine instructions by a compiler. **The compiler is a special program that gathers all of the source code files and generates instructions that can be run on the computer, such as by the Linux kernel**.

Commercial software has been sold under a closed source license, meaning that users have the right to use the machine code, also known as the binary or executable, but cannot see the source code. Often the license explicitly states that users may not attempt to reverse engineer the machine code back to source code to figure out what it does.

**Consider This**: Source code compiled into binary programs is one method of creating programs and running computing instructions. Another is the many types of interpreted languages, such as PERL, Python and even BASH scripting, where the code is not compiled, but fed to an interpreting program, typically a binary executable that understands and implements the instructions contained in the source code or scripts.

**The development of Linux closely parallels the rise of open source software**. Early on there was shareware, freely available programs where users did not necessarily have access to the source code. There were a lot of good things about this, but it was also problematic because malicious programs could be disguised as innocent-looking games, screensavers, and utilities. 

**Open source takes a source-centric view of software**. The **open source philosophy is that users have the right to obtain the software source code, and to expand and modify programs for their own use**. This **also meant the code could be inspected for backdoors, viruses, and spyware**. By creating a community of developers and users, accountability for bugs, security vulnerabilities, and compatibility issues became a shared responsibility. This new, global community of computer enthusiasts was empowered by the growing availability of faster internet services and the world wide web.

**Linux has adopted this philosophy to great success**. **Since Linux was written in the C programming language, and it mirrored the design and functionality of already established UNIX systems, it naturally became a forum where people could develop and share new ideas**. Freed from the constraints of proprietary hardware and software platforms, large numbers of very skilled programmers have been able to contribute to the various distributions, making for software that is often more robust, stable, adaptable, and, frankly, better than the proprietary, closed source offerings which dominated the previous decades.

### 4.2 Open Source Licensing

When talking about buying software, there are three distinct components:

* Ownership: Who owns the intellectual property behind the software?
* Money Transfer: How does money change hands, if at all?
* Licensing: What do you get? What can you do with the software? Can you use it on only one computer? Can you give it to someone else?

**Two contrasting examples will get things started.**

**With Microsoft Windows**, the **Microsoft Corporation owns the intellectual property**. The license itself, the **End User License Agreement (EULA), is a custom legal document that you must click through, indicating your acceptance, in order to install the software**. **Microsoft keeps the source code and distributes only binary copies through authorized channels**. For most consumer products you are allowed to install the software on one computer and are not allowed to make copies of the disk other than for a backup. You are not allowed to reverse engineer the software. You pay for one copy of the software, which gets you minor updates but not major upgrades.

**Linux is owned by Linus Torvalds**. **He has placed the code under a license called GNU General Public License version 2 (GPLv2). This license, among other things, says that the source code must be made available to anyone who asks and that anyone is allowed to make changes**. One caveat to this is that **if someone makes changes and distributes them, they must put the changes under the same license so that others can benefit**. **GPLv2 also says that no one is allowed to charge for distributing the source code other than the actual costs of doing so (**such as copying it to removable media).

In general, **when someone creates something, they also get the right to decide how it is used and distributed**. **Free and Open Source Software (FOSS)** refers to software where this right has been given up; anyone is allowed to view the source code and redistribute it. Linus Torvalds has done that with Linux – even though he created Linux he can’t forbid someone from using it on their computer because he has given up that right through the GPLv2 license.

Software licensing is a political issue, therefore it should come as no surprise that there are many different opinions. Organizations have come up with their own license that embodies their particular views, so it is easier to choose an existing license than come up with your own. For example, universities like the Massachusetts Institute of Technology (MIT) and University of California have come up with licenses, as have projects like the Apache Foundation. Also, groups like the Free Software Foundation have created their own licenses to further their agenda.

#### 4.2.1 The Free Software Foundation 

Only a few years after the development of the GNU project, Richard Stallman founded the Free Software Foundation (FSF) in 1985 with the goal of promoting free software. In this context, the word "free" does not refer to the price, but to the freedom to share, study, and modify the underlying source code. According to their website, the FSF believes that users should have "control over the technology we use in our homes, schools, and businesses".

FSF also advocates that software licenses should enforce the openness of modifications. It is their view that if someone modifies free software that they should be required to share any changes they have made when they share it again. This specific philosophy is called copyleft. According to FSF, "copyleft is a general method for making a program (or other work) free (in the sense of freedom, not "zero price"), and requiring all modified and extended versions of the program to be free as well".

The FSF also advocates against software patents and acts as a watchdog for standards organizations, speaking out when a proposed standard might violate the free software principles by including items like Digital Rights Management (DRM) which restrict what can be done with compliant programs.

The FSF have developed their own set of licenses which are free for anyone to use based on the original GNU General Public License (GPL). FSF currently maintains GNU General Public License version 2 (GPLv2) and version 3 (GPLv3), as well as the GNU Lesser General Public Licenses version 2 (LGPLv2) and version 3 (LGPLv3). These licenses are meant to be included in the actual source code to ensure that all future variants and modifications of the original program continue to have the same freedom of use as the original. The GPL license and its variants are powerful legal tools to advance the cause of free software worldwide. What started off in 1983 as one man’s desire to share and improve software by letting others change it has ended up changing the world.

**Consider This**: The changes between GPLv2 and GPLv3 largely focused on using free software on a closed hardware device which has been coined Tivoization. TiVo is a company that builds a television digital video recorder on their own hardware and used Linux as the base for their software. While TiVo released the source code to their version of Linux as required under GPLv2, the hardware would not run any modified binaries. In the eyes of the FSF, this went against the spirit of the GPLv2, so they added a specific clause to version 3 of the license. Linus Torvalds agrees with TiVo on this matter and has chosen to stay with GPLv2.

#### 4.2.2 The Open Source Initiative

The Open Source Initiative (OSI) was founded in 1998 by Bruce Perens and Eric Raymond. They believed that the Free Software Foundation was too politically charged and that less extreme licenses were necessary, particularly around the copyleft aspects of FSF licenses. OSI believes that not only should the source be freely available, but also that no restrictions should be placed on the use of the software, no matter what the intended use. Unlike the FSF, the OSI does not have its own set of licenses. Instead, the OSI has a set of principles and adds licenses to that list if they meet those principles, called open source licenses. Software that conforms to an Open Source license is, therefore, open source software.

One type of Open Source license is the BSD (Berkeley Software Distribution) and its derivatives, which are much simpler than GPL. There are currently two actual "BSD" licenses approved by OSI, a 2-Clause and a 3-Clause. These licenses state that you may redistribute the source and binaries as long as you maintain copyright notices and don’t imply that the original creator endorses your version. In other words "do what you want with this software, just don’t say you wrote it." According to FSF, the original BSD license had a serious flaw in that it required developers to add a clause acknowledging the University of California, Berkeley in every advertisement for software licensed this way. As others copied this simple license, they included acknowledgment for their own institutions which led to over 75 such acknowledgments in some cases.

FSF licenses, such as GPLv2, are also open source licenses. However, many open source licenses such as BSD and MIT do not contain the copyleft provisions and are thus not acceptable to the FSF. These licenses are called permissive free software licenses because they are permissive in how you can redistribute the software. You can take BSD licensed software and include it in a closed software product as long as you give proper attribution.

Rather than dwell over the finer points of Open Source and Free Software, the community has started referring to them collectively as Free and Open Source Software (FOSS). The English word "free" can mean "free as in lunch" (as in no cost) or "free as in speech" (as in no restrictions). This ambiguity led to the inclusion of the word "libre" to refer to the latter definition. Thus, we end up with Free/Libre/Open Source Software (FLOSS).


#### 4.2.3 Creative Commons

FOSS licenses are mostly related to software. People have placed works such as drawings and plans under FOSS licenses, but this was not the intent.

When **software has been placed in the public domain, the author has relinquished all rights, including the copyright on the work**. In some countries, this is the default when the work is done by a government agency. In some countries, copyrighted work becomes public domain after the author has died and a lengthy waiting period has elapsed.

The **Creative Commons (CC) organization has created the Creative Commons Licenses which try to address the intentions behind FOSS licenses for non-software entities**. **CC licenses can also be used to restrict commercial use if that is the desire of the copyright holder**. **The CC licenses are made up of the following set of conditions the creator can apply to their work**:

* Attribution (BY) – All CC licenses require that the creator must be given credit, without implying that the creator endorses the use.
* ShareAlike (SA) – This allows others to copy, distribute, perform, and modify the work, provided they do so under the same terms.
* NonCommercial (NC) – This allows others to distribute, display, perform, and modify the work for any purpose other than commercially.
* NoDerivatives (ND) – This allows others to distribute, display, and perform only original copies of the work. They must obtain the creator’s permission to modify it.

These conditions are then combined to create the six main licenses offered by Creative Commons:
* Attribution (CC BY) – Much like the BSD license, you can use CC BY content for any use but must credit the copyright holder.
* Attribution ShareAlike (CC BY-SA) – A copyleft version of the Attribution license. Derived works must be shared under the same license, much like in the Free Software ideals.
* Attribution NoDerivs (CC BY-ND) – You may redistribute the content under the same conditions as CC-BY but may not change it.
* Attribution-NonCommercial (CC BY-NC) – Just like CC BY, but you may not use it for commercial purposes.
* Attribution-NonCommercial-ShareAlike (CC BY-NC-SA) – Builds on the CC BY-NC license but requires that your changes be shared under the same license.
* Attribution-NonCommercial-NoDerivs (CC BY-NC-ND) – You are sharing the content to be used for non-commercial purposes, but people may not change the content.
* No Rights Reserved (CC0) – This is the Creative Commons version of public domain.

### 4.3 Open Source Business Models

If all this software is free, how can anyone make money off of it?

First, you must understand there isn’t anything in the GPL that prohibits selling software. In fact, the right to sell software is part of the GPL license. Again, recall that the word free refers to freedom, not price. Companies that add value to these free programs are encouraged to make as much money as they can, and put those profits back into developing more and better software.

One of the simplest ways to make money is to sell support or warranty around the software. Companies like Canonical, the developer of Ubuntu, and Redhat have grown into huge enterprises by creating Linux distributions and tools that enable commercial users to manage their enterprises and offer products and services to their customers.

Many other open source projects have also expanded into substantial businesses. In the 1990s, Gerald Combs was working at an Internet service provider and started writing his own network analysis tool because similar tools at the time were costly. Over 600 people have now contributed to the project, called Wireshark. It is now often considered better than commercial offerings and led to a company being formed to sell products and support. Like many others, this company was purchased by a larger enterprise that supports its continued development.

Companies like Tivo have packaged hardware or add extra closed source software to sell alongside the free software. Appliances and embedded systems that use Linux are a multi-billion dollar business and encompass everything from home DVRs to security cameras and wearable fitness devices. Many consumer firewalls and entertainment devices follow this model.

Today, both large and small employers have individuals and sometimes whole groups devoted to working on open source projects. Technology companies compete for the opportunity to influence projects that will shape the future of their industries. Other companies dedicate resources towards projects they need for internal use. As more business is done on cloud resources, the opportunity for open source programmers continues to expand.

### Key Terms

* **BSD**: An open source license which states that you may redistribute the source software and binaries as long as copyright notices are maintained and there is no implication that the original creator endorses your version. Short for Berkley Software Distribution. Section 4.2.2 
* **Creative Commons**: An organization created to address the intentions behind FOSS licenses for non-software entities. Section 4.2.3 
* **FLOSS**: Free/Libre/Open Source Software (FLOSS) is a collective term for the open source community which uses the term libre to define the difference between free from restrictions on software usage (libre) and free from cost (free). Section 4.2.2.
* **FOSS**: An open source body called Free Open Source Software (FOSS) which consists of both Free Software and Open Source as a collective in order to downplay the differences between the two organizations. Section 4.2.2 
* **Free Software**: The freedom to share, study and modify the underlying source code of the software. Section 4.2.1 
* **GPL**: Licenses developed by FSF that are meant to be included in the source code to ensure that all future variants and modifications of the original program continue to have the same freedom of use as the original. Short for GNU General Public Licenses. Section 4.2.1 
* **Open Source Software**: Software that meets the OSI Open Source software guidelines where no restrictions are placed on the use of the software regardless of the intended use. Section 4.2.2 
* **copyleft**: A philosophy held by the Free Software Foundation (FSF) that someone who modifies free software should be required to share any changes they have made. Section 4.2.1 
* **open source business models** Section 4.3 
* **permissive**: Open source licenses that do not contain copyleft provisions and therefore are more permissive in how they allow software to be redistributed. Section 4.2.2 

