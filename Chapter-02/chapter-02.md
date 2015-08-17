# History of Unix and Linux

![*At the end of class you will find this cartoon funny*](http://imgs.xkcd.com/comics/open_source.png "Understanding the Technology and Philosophy of Linux Part I")

[*If you still don't like it, that's OK: that's why I'm boss. I simply know better than you do. Torvalds, Linus(1996-07-22)*](http://groups.google.com/groups?selm=4sv02t%24j8g%40linux.cs.Helsinki.FI "Quote from Linus Torvalds")

## - The Foundation of Unix and Linux

Why are you learning about Linux?  It is a term that seems to be on everyone's lips.  There is a good chance that you even have Linux running in your pocket and don't even know it! Raise your hand if you have an Android based phone or tablet? Here is a hint, Android Operating System is based off of Linux.  So this chapter begins the start of your mastery of Linux.  In addtition to teaching you technology, this book aims to teach you about the history and philosophy of Linux so you can understand where it came from and where it is going and why you are using it.  Some pieces of this book will seem frustrating, after all the roots of the design decisions of what we are using today are 30-40 years old in some cases.  Helping to understand what kind of technology was available and what these creators were thinking will help you master the concepts of Linux.

__Chapter 2 Objectives__

  * Understand how the Unix Operating System was created 
  * Understand the contributions of Ken Thompson and Dennis Ritchie to Unix
  * Understand the contributions of Richard Stallman to Unix, Linux, GNU, and FOSS
  * Understand the contributions of Linus Torvalds to the creation of Linux
  * Understand the nature of modern commercial implementations of Linux
  * Understand the principles of the Linux Community and what the *"free"* in *"Software Freemom"* means

__Outcomes__
 
 At the completion of this chapter a student will understand and be able to discuss the environment in which Unix and Linux were created. They will be able to relate key names; *Thompson, Ritchie, Stallman, and Torvalds* to their technilogical contributions.  They will be able to understand what Linux and Unix are and how they relate to FOSS and commercial softare.

*Convention Note*

  You will notice that I have been using the terms Unix and Linux interchangably so far.  For a large part of this book the conventions are the same - their history is intertwined. Though this book focuses on Linux we would be depriving you of the full truth if we left Unix out.  For this first chapter then we need to understand their related history.  There are differences and there are similarities.  

## - Where it Began and Why it Matters Now 
 
  When we say *"Unix"* we are referring to an entire operating system.  An Operating System can be boiled down into three main parts.   

  1.  __Kernel__
 
  <a title="By Bobbo (Own work) [CC BY-SA 3.0 (http://creativecommons.org/licenses/by-sa/3.0) or GFDL (http://www.gnu.org/copyleft/fdl.html)], via Wikimedia Commons" href="https://commons.wikimedia.org/wiki/File%3AKernel_Layout.svg"><img width="256" alt="Kernel Layout" src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/8f/Kernel_Layout.svg/256px-Kernel_Layout.svg.png"/></a>
    
  Unix includes a kernel - a hardware abstraction layer that handles all the interfaces from the operating system to the hardware.  The kernel is the portion of the Operating system that allows you to write once and interface with hardware through drivers.  Otherwise you would have to compile the operating system everytime and include the hardware drivers for your hardware.  Take Windows for instance - you have just one version for all of the hardware out there.  Intel Chips, AMD processors, Marvell, Broadcom, and many others.  But there is no need to buy a version of Windows, Mac, or Linux specific to that hardware - software drivers are inserted into the kernel and allow Windows, Mac, or Linux to simply communicate with the hardware.  Think of the Kernel liek the engine of a car.  
  
  2. __User Interface and Operating System Tools__
 
  All operating systems need a way for a user to interface with the kernel.  This is where the Shell and User Applications come into play.  The Shell is a way for you as the user to send commands to the operating system--which executes these commands through the kernel.  Unix originally didn't have a graphical user interface, its time of being developed in the 70's precluded this. Once CRT monitors became prevelant the commandline shell became the standard interface.  This allowed you to type commands direclty on a screen and see the results back--no paper involved.  Eventually the [X Windows System](https://en.wikipedia.org/wiki/X_Window_System) came along giving you the familiar desktop windows you are most likely used to, allowing for mouse and keyboard input.  X Windows is the standard windowing toolkit that prety much all versions of Linux GUI build upon today.   

  Operating System tools include simple tools you take for granted like copy, delete, move, make directory, kill a process, open a text editor to modify a file, issue a compile command to the C compiler, or redirect output from the screen to a file.  All these tools and more are included in Unix as an operating system.
  
  User applications like a web browsers and email clients are seen as tools that are created by the user that just repurpose the existing Operating System tools and are built/installed by the user.

  3.  __Programming Language and Compiler Tools__

  In the modern GUI comuting world we are used to just clicking on .exe or .dmg files and off our installation of Chrome or Firefox goes.  In the Unix world all software is built using the C language.  You needed a compiler to build the kernel, operating system, system applications, user tools, and any additional tools you create. Without a C compiler you cannot build or make anything.  Today most code is pre-compiled for you and you can use other languages, but in the early days of Unix and Linux a C Compiler was neccesary as you were building the kernel, operating system, and tooling from scratch.  
 
__Linux is the same as Unix but...__
 
  Linux on the otherhand is technically not a full operating system like Unix.  It is actually just a kernel, and is missing all the other tools listed above, though you will hear people refer to it as an operating sysetm.  Depending on your audience you need to know both facets.  The Linux kernel plus someone elses User Interface and Operating System Tools and Programming Language and Compiler Tools and premade user applications makes up a Linux distribution or simply Linux distro. Every company and person can equally contribute to the Linux kernel and make their own distributions.  Linux was built out of the Unix world, keeping all the same conventions and ideas from Unix but starting in a different place.  I think a good analogy would be the American Colonies in 1776 - they thought of themselves as Europeans, they came out of Europe but yet were starting new in America.   

__Take away point__
  
  Who uses Linux today?  
  
  * Facebook
  * RedHat
  * Oracle
  * [Google](http://highscalability.com/google-architecture "You Tube Architecture" ) 
  * Amazon
  * RedHat
  * NYSE- [New York Stock Exchange](https://en.wikipedia.org/wiki/New_York_Stock_Exchange)
  * CME - [Chicago Mercantile Exhcange](https://en.wikipedia.org/wiki/Chicago_Mercantile_Exchange)
  * IBM
  * Android
  * [Microsoft](https://en.wikipedia.org/wiki/History_of_Linux#Competition_from_Microsoft "2009 submitted 12,00 Lines of Code to the Linux Kernel") 
  * [Pretty much every top website except Stackoverflow.com](http://highscalability.com/all-time-favorites/ "Architectures")
  
  The question is not who uses Linux but the question should be when did you last use it?  How did it get this way?  Where did it come from?  Ignore this part at your own peril, you will never understand Linux unless you understand UNIX at its core philosophies.  Here we go.

### - Thompson, Ritchie, and Bell Labs

  Many people supported and worked on what would become known as Unix but two names have received most of the credit for the creation, promotion, and use of Unix.  *__Know these names.__*
  
__Ken Thompson and Dennis Ritchie__

<a title="See page for author [Public domain], via Wikimedia Commons" href="https://commons.wikimedia.org/wiki/File%3AKen_n_dennis.jpg"><img width="256" alt="Ken n dennis" src="https://upload.wikimedia.org/wikipedia/commons/3/36/Ken_n_dennis.jpg"/></a>
    
  Without Thompson and Ritchie, there would be no Unix and most likely no Linux today.  Until recently both were hired as Distinguished Engineers at Google.  Dennis Ritchie passed away in 2011. Ken Thompson is still working and recently help produce the [Go programming language](https://en.wikipedia.org/wiki/Go_(programming_language) from Google. 

  To begin We need to go back to 1968.  The Unix project got it start in something called MULTICS, which was an attempt to build a multi-user operating system.  At the time, this combined all the brightest minds of General Electric, MIT, ARPA, and Bell Labs.  Now today those aren't names you think of when you think of computers.  Yet in 1968/1969 General Electric and the government (ARPA) were the large funders and suppliers of computing (The PC market we know of today doesn't come until 1984!).

  Bell Labs was basically the *"idea shop"* of the entire country - where the best and brightest went to invent everything we take for granted today. Bell Labs was spun off by AT&T and became Lucent Technologies, which became Alcatel-Lucent and now is soon to be part of Nokia. One could argue that Google and Facebook have taken its place  where the brightest minds go to invent new things in America.  No wonder that Dennis Ritchie, Ken Thompson, Brian Kernighan and even James Gosling (creator of the Java programming language) are and were employees at Google.

  Like all projects that try to do to much, MULTICS stalled in gridlock between the different companies and the demands of the government.  This left one crafty engineers with much free time and (for those days) a true rarity - unused copmuters; PDP-7s to be exact.  Ken Thompson had an insiders view of the innovative things MULTICS was trying to accomplish and why the inner workings of the MULTICS project went wrong. Thompson also had a job to do as a Bell Labs researcher.  On his own time and down time, he began to use these PDP7's and program his own multi-user operating sysetm, but with a different twist.  It was designed by him, and solved daily work and coding problems he had.  This operating system and its tools was then a project to help him get his own work done more efficiently.   

__PDP7__

<a title="By en:User:Toresbe [CC SA 1.0 (http://creativecommons.org/licenses/sa/1.0/)], via Wikimedia Commons" href="https://commons.wikimedia.org/wiki/File%3APdp7-oslo-2005.jpeg"><img width="512" alt="Pdp7-oslo-2005" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/52/Pdp7-oslo-2005.jpeg/512px-Pdp7-oslo-2005.jpeg"/></a>

For this time, 1969-70, this is something radically new. Thompson had no idea that his pet work project was going to become part of a computing revolution.  Where as MULTICS and other computer systems were designed by committees and based on marketable features--due to the nature of the up front financial investment, Unix was simple and easy to build because it solved only a small set of problems--which turned out to be the same problems every engineer had.  The overall reason that Unix took hold was that it was designed by engineers to solve other problems that engineers were having--enabling them to get work done.  This was pure genius and this is how Ken Thompson's mind worked.  

Unix differences from existing commercial Operating Systems

  * Written by Ken Thompson on his spare time
  * No company owned it or committee designed it for commercial purposes
  * Solved problems that engineers had
  * Built by engineers
  * Had a consistent design philosophy
  * Designed to be portable and work on many hardware vendor platforms

Thompson's Unix success was also a by product of its main design philosophies:

  *  Everything is a file 
    + This means that everything can be read from or written to: All the way from devices to text files
  *  Unix Portable -- everything written in C
  *  Unix is a collection of small tools that do one and only one thing well
    + To build complex tools you chain input and output of tools together with *pipes* -> "|"
 *  The only file format used in Unix is plain ASCII text 
    +  Yes, there are compiled binaries but you generally are not reading and writing directly to them 
    
 Between 1970 and 1974 Unix grew in its maturity.  And one of its crowning achienvements--its portability came to life.  Unix was originally written in assembly lanugage for the PDP-7. It needed to be as low level code as possible because disk storage space was a HUGE premium in those days.  This was good, but the problem with writting in low level assembly means that the code is optimized to only run on a PDP-7 system.  Not on a PDP-11 or a DEC Vac, or an IBM 360, etc, etc.  So what you gain in efficiency you lose in portablitiy.  What good is Unix if it could only be used on a PDP 7? It would have stayed a Bell Labs pet project.
 
 While Thompson was builing Unix his fellow engineers at Bell Labs got wind of what he was doing and asked to have access to his system, and then to be able to contribute additonal functionality.  Enter Dennis Ritchie, who championed Ken Thompson's Unix in Bell Labs.  Ritchie was a computer language creator and saw the utility of Thompson's Unix, but realized it was trapped in PDP7 assembler language.  Today we take for granted high level lanugages like C, C++, Python, and Java.  In the early 1970's these did not exist.  Ritchie's initial work was on a high level language that could be built in order to compile and run the same code on two different operating systems. His initial work was on a [language called "B"](https://en.wikipedia.org/wiki/B_(programming_language "B Lanugage") which was derived from a language called BCPL.  B was designed to execute applications and operating system specific tasks but didn't handle numeric data (a feature actually to save precious harddrive space). B was also missing many other features you would expect in modern programming languages.  
 
 What happened was that Thompson and Ritchie went to work extending "B" with all the features they would need to make an operating system fully function and portable.  They called this language surprsingly, "C" -- the same "C" lanugage you know today.  C was different from assembler in that is resembled assembler code syntx had a high enough level of abstraction that the "C" code was an independant language.  With the advent of C - Unix was rewritten in this language.  With the creation of C compilers for different hardware, Unix could now be built and be recomplied on different architectures, PDP-7, PDP-11, DEC VAX, DEC Alpha, IBM 360, SUN SPARC etc, etc.  
 
![C Programming language "Hello World!"](images/hello-c.png "C language") ![Intel x86 Assembly code of "Hello World!"](images/hello-asm.png "Assembly Language")   
 
Since Ritchie created "C" to solve all the problems Unix had -- it became the defacto lanuage of Unix and from that point on pretty much all operating systems are designed in "C" after Thompson and Rithie showed that you could use a high level lanuage to make Unix portable accross many platforms.  

__Brian Kernighan__

<a title="By Ben Lowe (https://www.flickr.com/photos/blowe/7984191331/) [CC BY 2.0 (http://creativecommons.org/licenses/by/2.0)], via Wikimedia Commons" href="https://commons.wikimedia.org/wiki/File%3ABrian_Kernighan_in_2012_at_Bell_Labs_1.jpg"><img width="256" alt="Brian Kernighan in 2012 at Bell Labs 1" src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/ae/Brian_Kernighan_in_2012_at_Bell_Labs_1.jpg/256px-Brian_Kernighan_in_2012_at_Bell_Labs_1.jpg"/></a>
  
  Thompson didn't have a name for his project initally, another realted figure, Brian Kernighan, can be credited with giving it the name UNIX.  This was a play on words-- MULTI vs UNI in the name. Kernighan also helped write the original C language text book along with Dennis Ritche (called K&R C -- some of you might have used when in school).
  
__Unix Maturity__

By 1974/75 Unix is growing in its maturity.  Other Bell Labs divisions get wind of this and begin to request "tapes" for their own use.  Tapes meant giant mounted magnetic tape reels that contained all the operating system installation code.  By law AT&T was prohibited from getting into the computer business so they could not turn this into a business.  AT&T left it curriously as Thompson and Ritchie's pet project.  Many Universities at this time--wanting to teach computing and operating systems began to request copies of Unix to teach in their Operating Systems classes.  This was attractive to universities because Unix was a fully operational and working system but the main draw was that the source code was freely given away by Ken Thompson.  You sent him a letter, paid for shipping, and you got a reel within a week or so.  Thompson had no concept of "ownership" and freely shared his project with anyone who was interested.    

In 1975 Ken Thompson took a sabbatical from Bell Labs and went back to his Alma Mater, Berkly, in California.  Installing the Version 6 Unix Release.  The students at Berkley loved Unix and started adding their own features to improve it to solve their own problems.  One student in 1978, Bill Joy, added vi and the C Shell (two things still in use today in modern Linux) and started redistributing his "re-mix" of Unix called BSD (Berkely System Distrubition.)  

By 1980, with many copies of Thompson's Unix now in circulation and nearly a decade of work you start to see fragmentation of the original Unix and many universities adding on their own customizations.  Since the code was technically propriaary under AT&T's ownership - there was no way to contribute code back to the source.  Unix starts to splinter.  Another problem AT&T had was that by the end of the 70's all those students who had learned Unix in college went to work in corporations and began to request Unix be used on their hardware platforms at work. Unix was the only operating system of its type kind that could do this.  Now AT&T had a financial motive to commercialize Unix.  By 1982 AT&T released Unix System III, followed by System V in 1983, as a commerical product outside of Bell Labs for sale to commerical companies, while adding a multi-hundred dollar academic fee too.  At this time the Berkley System Distribution of Unix was beginning to vary widly in functionality from commcerial AT&T UNIX. You see derivates of Unix like SunOS and SCO Unix being released as commerical companies based of BSD Unix.  With HP/UX and IBM AIX being based on AT&T System V.  The focus of Unix takes a dramatic shift now as the implementation portion is finished.  Now the spoltlight moves to users and application creation. Enter Richard Mathhew Stallman, known also as RMS a researcher at the AI Labs at MIT who moves the discussion of software and *"software freedom"* into the spotlight.  

### - Richard Stallman and GNU

<a title="By Dkoukoul (Own work) [CC BY-SA 4.0 (http://creativecommons.org/licenses/by-sa/4.0)], via Wikimedia Commons" href="https://commons.wikimedia.org/wiki/File%3ARichard_Stallman_at_CommonsFest_Athens_2015_2.JPG"><img width="256" alt="Richard Stallman at CommonsFest Athens 2015 2" src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/a8/Richard_Stallman_at_CommonsFest_Athens_2015_2.JPG/256px-Richard_Stallman_at_CommonsFest_Athens_2015_2.JPG"/></a>

Before beginning anything in dealing with Richard Stallman there is one critical concept you need to understand: "software freedom."  Often times you hear as a selling point that Linux is a good operating system to use because it is free -- as in there is no cost.  Stallman is not advocating about cost or the ability to charge money for software.  This is a common confusion.  He is advocating that the software itself is *"free"* as in freedom and that the user has the freedom to modify and or inspect its content and redistribute the original source.  Ricahrd Stallman belives this is not a question of legality but of moral consequence and thereby will not use any non-free software period.  When dealing with Stallman this is the fundamental fact you need to know.

Ricahrd Stallman was a student and a researcher at MIT in the early 1980's.  He was part of what you would call today a hacker culture that was constantly researching and developling new tools and applications.  As Richard Stallman progressed in his time at MIT he began to encounter events that he saw as counter intuative hacker culture that had been created at MIT by 1984.  The spirit of Ken Thompson and the free and sharing culture of Unix was strong with these Jedi.  Small things such as the addition of usernames and passwords on the school computer networks were seen as obstacles. Stallman saw the removal of the capability to modify a network printer's firmware to send an email feature in case of a paper jam as well as the beginning of propriatary software lock in--hindering the ability of the users to inspect the code and improve it to serve their needs.  By 1984 AT&T began to withhold the source code of Unix and restric access of those in the academic world to be able to use the AT&T source code. By 1983 Stallman began to argue that the users of the software's freedom were being trampled on. Users were now beholden to the closed nature of the prodcuts they were using--even if they had paid for the software.  Stallman saw this as more than an inconvienience and set about making it his life's work to rectifiy this issue.

__GNU Manifesto__

  A plan began to hatch in his mind.  Since Unix was the popular operating system at the time Stallman would make a call, a manifesto, for his GNU project to basically reverse engineer all the funcitonality, capability, and tooling of Unix--__BUT__ without the propriatary and restricitve licenses with the source code being freely shared.  

  He felt strongly enough to announce the GNU project publicly in th fall of 1983, and to quit his job working in the MIT lab in 1984 to avoid conflict of interests and persue this work.  Richard wrote his GNU manifesto stating his plans in Oct 3rd, 1985 and issuing a general call to arms in the [GNU Manifesto.](http://www.gnu.org/gnu/manifesto.html "GNU Manifesto") Here is the opening paragraph from the manifesto.
 
> __Why I Must Write GNU__

> *"I consider that the Golden Rule requires that if I like a program I must share it with other people who like it. Software sellers want to divide the users and conquer them, making each user agree not to share with others. I refuse to break solidarity with other users in this way. I cannot in good conscience sign a nondisclosure agreement or a software license agreement. For years I worked within the Artificial Intelligence Lab to resist such tendencies and other inhospitalities, but eventually they had gone too far: I could not remain in an institution where such things are done for me against my will."*
> 
> *"So that I can continue to use computers without dishonor, I have decided to put together a sufficient body of free software so that I will be able to get along without any software that is not free. I have resigned from the AI Lab to deny MIT any legal excuse to prevent me from giving GNU away."*

  GNU is a recursive acronym meaning *"GNU's not Unix."*  Stallman wanted to let people know his project was Unix like in fucntionality but not goverened by Unix's restricitve licensing.  His passion was to develop a fully free operating system so that everyone who could use a computer could have access to a *"free"* operating system.  Stallman is a brilliant man who had the capability to build an OS from scratch, but the project became more than a one man job.

__Free Software Foundation and GPL__

 In late 1985 the [FSF](http://www.fsf.org/ "FSF") -- Free Software Foundation was formed to be the holder of all the intellectual property of the GNU project. By 1989 a new role for the FSF arose. Commercial entities were starting to take notice and corrupt the idea of free software and the FSF needed a way to protect their software freedoms.  But how?  Copyright was restrictive and would make the FSF no different from the commercial entities that restrict freedom.  Public Domain offered no legally enforceable protections.   So enter Copyleft--which is a hack on the term copyright in the form of the [GPL - GNU Public License.](https://en.wikipedia.org/wiki/GNU_General_Public_License "GPL")  It flips copyright over by basically saying, you need to freely distribute the source code of any project lisenced under GPL, you need to attribute where your source came from, and that you cannot restrict any of these rights to any future derivative work.  Meaning that you cannot close source some open source code that is GPL'd.  This is different from the *"permissive open source licenses"* BSD, MIT, and Apache licenses which can have derivative works closed source.

__GNU HURD__

  All seemed to be going well. RMS started this work of creating a free Unix-like operating system.  Since Unix was built upon the C programming Language, the first thing needed to build a kernel, a shell, and tools was a C compiler.  This project was called GCC or GNU C Compiler which was an *"free"* version of the propriatary Unix AT&T "cc" program or C Compiler.  Next Stallman needed a text or screen editor to edit files and run his compiler tools to build software.  In 1981 James Gosling has created the Gosling Emacs editor.  James Gosling would later go on to create the Java programming language while at Sun in 1994.  Stallman almost single handedly rewrote all of [Goslings code in gmacs](https://en.wikipedia.org/wiki/Gosling_Emacs "Gosling Stallman and Emacs") to produce a *"free"* version of Emacs - now over 30 years old and still in use. The project continued on to now basic Operating System commands such as [ls, grep, awk, make and ld.](https://en.wikipedia.org/wiki/GNU_Project "Commands")   Eventually an entire "zoo" of projects were created and are listed and described here: [other GNU tools](http://www.gnu.org/manual/blurbs.html) were added by contributers and volunteers.  They did remarkably well and had reverse engineered and in some cases improved the components of Unix by 1991 (8 years of work). They built everything except 1 critial piece...  they didn't have a kernel for their operating system.  Turns out that writing a kernel is much harder than it looks.  
 
  A project was started called [GNU Hurd](http://www.gnu.org/software/hurd/ "GNU Hurd") to be the kernel for the GNU operating system in 1985. The term GNU Hurd is also another clever recursive hack.  Since GNU has a double meaning.  There is a [large goat like animal called a gnu](https://en.wikipedia.org/wiki/Wildebeest "GNU"), which lives in herds that roam the plains of Africa.  The name HURD came from the idea of a herd of animals and the fact that the design of the GNU Kernel would be a "herd" of small micro-processes comminicating together.  It seems that GNU hackers really loved cleaver hacks.  It it something that you have to get used to in opensource as the spirit of bad puns and clever hacks has carried on to this day.
  
  Hurd made some false starts in its initial micro-kernel development phase causing multiple versions to be created and scrapped.  What they were trying to do was really innovative but really complicated to have it work reliably. In retrospect HURD was never finished.  By 1998 The GNU project had all but stopped active development and promotion of GNU HURD as the kernel for its free operating system.  The GNU project realized that the Linux Kernel had accomplished what GNU was trying to do in a matter of 4 years and in a more clever way.  
  
  GNU HURD is currently in a usable alpha stage [and downloadable today](http://www.gnu.org/software/hurd/ "GNU HURD Download") by joining it with the Debian Linux distribution applications--all GPL approved mind you. 
  Instead recommends the Linux kernel instead.  In someways this was the realization of Stallman's dream and yet someways this was his biggest disappointment that Linus Torvalds and not the GNU project finished the kernel.  By 1991 the Linux kernel pops onto the scene and we have another little revolution in the free and open computing world.  Thompson -> Stallman -> Torvalds.
  
### - Minix, Linus Torvalds, and Linux 

__Minix__

  Before we talk about the Linux kernel, we need to talk about the Minix operating system.  With the closing off of the AT&T Unix source code by 1984 to academics and researchers in the university - they were left without source to show as examples.  One professor [Andrew S. Tanenbaum](http://www.cs.vu.nl/~ast/ "Tanebaum's website") teaching at  Vrije Universiteit in Amsterdam - began to write and implement his own Unix-like operating system but only for teaching and demonstroation purposes.  It was 12,000 linees of C code and system call compatible with commerical Unix.  The name [Minix](http://www.minix3.org/ "Minix 3 website") was a combination of "minimal" and "Unix."  Minix 1.0 and 1.5 were released in 1987 and 1991 respectively with the original purpose as only a teaching tool. Minix 1.0 and 1.5 were freely avaialable to anyone as the source code came in the appendix to a text book about operating systems written by Tanenbaum in 1987.  Minix was designed to run initall on older x86 Intel processors and in version 1.5 Sun Sparc processors.  These were common desktop stations in use at the university at that time.  Any enterprising student could find and old 8086 PC or old Sun Sparc Station to run it on. The source code for Minix 3 is currently available in a [git repository](http://git.minix3.org/index.cgi "Minix git") and is still being developed and researched.  In 1991 many people believed that Minix could have been a viable alternative to commercial Unix and become the still missing GNU Hurd kernel.  But the Minix creator, Professor Tanenbaum, was not interested in moving into this space and the code was no where near as mature as the Unix code base, which by 1991 had been in existance for almost 20 years!  Minix appears on the radar but was not the missing piece to the GNU puzzle.   
  
  <a title="By GerardM (Own work) [GFDL (http://www.gnu.org/copyleft/fdl.html), CC-BY-SA-3.0 (http://creativecommons.org/licenses/by-sa/3.0/) or CC BY 2.5 (http://creativecommons.org/licenses/by/2.5)], via Wikimedia Commons" href="https://commons.wikimedia.org/wiki/File%3AAndrewTanenbaum.JPG"><img width="256" alt="AndrewTanenbaum" src="https://upload.wikimedia.org/wikipedia/commons/c/c3/AndrewTanenbaum.JPG"/></a>

  Professor Andrew S. Tanenbaum

__Linux__

  <a title="By Krd (Own work) [CC BY-SA 3.0 (http://creativecommons.org/licenses/by-sa/3.0) or CC BY-SA 4.0 (http://creativecommons.org/licenses/by-sa/4.0)], via Wikimedia Commons" href="https://commons.wikimedia.org/wiki/File%3ALinuxCon_Europe_Linus_Torvalds_03.jpg"><img width="256" alt="LinuxCon Europe Linus Torvalds 03" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/52/LinuxCon_Europe_Linus_Torvalds_03.jpg/256px-LinuxCon_Europe_Linus_Torvalds_03.jpg"/></a>
  
  __Linus Torvalds__

  The Linux kernel comes to us from a graduate student named Linus Torvalds who developed it while at the University of Helsinki in Finland in 1991.  As a student Torvalds was using Unix on the universities Sun Sparc Stations.  He was not pleased with SunOS but felt it was the best of the commercial Unixes.  His real dream was to set out to run his own Unix like operating system on his own personal PC.  He had recently purchased an Intel x386 processor based desktop PC.  Linus tried Minix, but was put off by its minimalist approach and realized it had some good design concepts but was not a complete Unix replacement.  In a fashion not unlike Ken Thompson, Tovalds set out in the early part of 1991 deciding to see if he could build his own kernel for his own operating system for his own use and purpose that was Unix-like but wasn't Minix.  
 
  This was very impressive feat for a single person. Torvalds himself acknowledged that if GNU Hurd had been ready or if at this time AT&T hadn't been suing BSD, he would have re-used their kernel work and not built his own. By August 25th of 1991 the initial release of the Linux kernel was posted online.  The quote from the beginning of the chapter was the basis of the initial post to Minix Usenet Newsgroup-(Bulletin board like precursor to the actual Internet - like Google Groups -- today you would use twitter). His initial work was not quite a full fledged system but really just a small kernel, a user shell (GNU Bash), a C Compiler (GCC) but it was like a crack in a damn - it would only get wider and bigger.
  
  By September of 1991 Linux kernel version 0.1 has been posted to the University of Helsinki FTP servers for public download.  By Feburary of 1992 Linux 0.12 kernel had been released.  At that time Linus decided to give the project a real license for its use.  Having seen Richard Stallman speak at the University of Helsinki a few years back, Linus was inspried and dedided to release the Linus Kernel under the GPL license.  This was the smartest thing anyone could have done.  Can you see the connection to the GNU project?   The reason we Linux is so popular is because of this fledgling kernel that worked enough for people to use, hack on, and build upon now had a governance structure that could accept code contributions and be avaiulable for commerical work as well.  Being GPL the Linux kernel was instantly compatible with all of the entire GNU project's tools base.  You instantly had the kernel that GNU was missing and the Linux kernel had all the tools and applications ready to be used.     
   
  People began downloading and compiling his kernel, adding GNU tools, and making a fully capable UNix-like operating systems.  Linus' brilliance comes not from ingenuety but comes from good engineering pricipals of knowing when not to go down dead-end developenent trails.  Torvalds work was not perfect but was good enough that others could take it and start to use it and improve it.  From 1992 to 2001 Linux grew rapidly in size and features and spawned commercial companies to sell and support Linux Distributions. Stallman's dream was being realized.  
    
   There should have been cause for great celebration with Linux and GNU coming together.  The FSF saw this as a victory for GNU and began calling the system GNU/Linux hoping that the FSF and free software would get the recognition it deserved.  But Linus Torvalds didn't see it that way.  He has a unique personality--perhaps a bit arrogant.  He just ignored the FSF's requests and people referred to what should have been GNU/Linux as just Linus, leaving the GNU part out even though all of their tooling is what made Linux possible.  This is a spot of contention with the FSF.  
    
  Linux Kernel unique attributes recap:
  
  * Developed to solve one person's problem of wanting his own Unix liek OS 
  * Released often
  * Accpeted contributions back
  * Released freely and protected by GPL license
  * Used existing GNU tools - no need to reinvent the wheel
  
  __Personality__
  
  Linus Torvalds has a renowned personality.  Some people thing it is a schtick or a comedy persona he puts on.  But he is very uncaring in relating to others and can be really mean and agressivly mean spirited to those who he has disagreemtns.  When approached about this Linus states that he only cares about the kernel and no one else matters to him.  These links below provide some points and counter points about Linus.  
  
*  [Torvald's right to offend](http://www.wired.com/2013/07/linus-torvalds-right-to-offend/ "rights")
*  [Torvald doesn't care](http://arstechnica.com/business/2015/01/linus-torvalds-on-why-he-isnt-nice-i-dont-care-about-you/ "Doesn't care")
*  [Linus response to previous article](http://arstechnica.com/business/2015/01/linus-torvalds-responds-to-ars-about-diversity-niceness-in-open-source/ "Response")

__AT&T and BSD Lawsuit__

  From August of 1991 to Feburary of 1992 there was a rush of interest in Linux development? But where did all these develoeprs come from?  Remember the Berkley System Unix Distribution?  In the late 80's and now 1990s its development had been flourishing.  It began to support features that not even AT&T's Unix had.  BSD was such alarge project through that not all of the original code that was given the Berkly under acadmeic license had been reqritten.  AT&T found its code in BSD Unix and took them to court.  In early 1992 there was a court order development injunction preventing work from being done on BSD Unix.  This was just the time that Linux kernel development, covered by GPL now, so there was no licensing encumberment, devlopment flourished.  By the time the lawsuit was finished in late 1993/1994 it was too late.  The Linux rocket had left the launch pad and was never coming back. 

### - Free Software vs. Open Source Software

By the year 1998 a new idea in the *"Free Spftare"* movement was rising.  The long expected GNU HURD kernel never arrived, being replaced by Linux.  You also begant to see a corporate interset in opensource.  With all the best intentions the term *"free"* in free software had an overriding air of being only about cost.  Many commercial entities were simply not interested or afraid because they were concerned about loosing the chance to make money or retain rights over programs they created.  Some developers seeing a chance to promote the quality and community to the larger commercial markert. These developers did not hold with the FSF's moral stance on free software as the ultimate argument in free software adoption. Instead they compared open development and open code as superior in quality and cost in cost reduction to closed source development.  They beleived opensource was a business process decision and not a moral decision.  Enter Eric S. Raymond.

__Eric S. Raymond__

<a title="By Erc_S_Raymond_and_company.jpg: jerone2 derivative work: Bilby (Erc_S_Raymond_and_company.jpg) [CC BY-SA 2.0 (http://creativecommons.org/licenses/by-sa/2.0)], via Wikimedia Commons" href="https://commons.wikimedia.org/wiki/File%3AEric_S_Raymond_portrait.jpg"><img width="256" alt="Eric S Raymond portrait" src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/e2/Eric_S_Raymond_portrait.jpg/256px-Eric_S_Raymond_portrait.jpg"/></a>

Eric S. Raymond is another developer considered a peer along with Ricahrd Stallman.  Eric was one of the first to embrace the Free Software idea and promote using free software.  He was so convinced by the free softeare and the open development method that took place with Linux that he penned a seminal paper that was later reprinted called, __"The Cathedral and the Bazaar."__  

  His main point was that by usual business practices - Linux should have been a massive failure and poorly implemented experiment.  But instead it was an unprecendented success.  His article examined why this is the case.  His conclusion was that the open source code and open design methodology treating your user as a valued resource was vital to opensource project success.  Based on this Raymond and [Bruce Perens](https://en.wikipedia.org/wiki/Bruce_Perens "Bruce Perens") founded the [Open Source Initiative (OSI).](http://opensource.org/ "OSI") Their goal was to promote free software but instead of focusing on the moral issus they focused on the desgin principals as producing superior software.  A quote from Raymond puts his opinion bluntly;
 
 > *As head of the Open Source Initiative, he argued that advocates should focus on the potential for better products. The "very seductive" moral and ethical rhetoric of Richard Stallman and the Free Software Foundation fails, he said, "not because his principles are wrong, but because that kind of language ... simply does not persuade anybody".* 
 > [Eric S. Raymond](https://en.wikipedia.org/wiki/Eric_S._Raymond#Open_source "Quote")

  The "Catherdral and the Bazaar" was also influential in helping the Netscape Corporation opensource their Netscape Web Browser code as the company went bankrupt under the name of the Mozilla project.  This code gave rise to what would eventually become the Firefox web browser in 2002--thanks to Raymond's writings.  The OSI was willing to make freedom compromises in order to make larger productivity gains with opensource software. The FSF will not compromise. Richard Stallman fired back in his article [Open Source Misses the Point](http://www.gnu.org/philosophy/open-source-misses-the-point.html "Open Source Misses the Point") The terms do overlap Free Software and Open Source but ultiamtely have two divergent meanings.   There has been some compromise in the naming [FLOSS, Free Libre and Open Source Software] (https://en.wikipedia.org/wiki/Free_software_movement "FLOSS"), Free and Libre Open Source Software -- but the FSF rejects any licensing that allows a user to restrict the use of "freedom" Code.  One arguemtn would be the existance of [DRM](https://en.wikipedia.org/wiki/Digital_rights_management "DRM") software.  The OSI group would not be opposed to push for open sourced DRM software.  But the FSF would be opposed to the entire concept of DRM--which is a tool they believe for restricting a users freedom. 

 You can read Raymond's two seminal books on Unix and Open Source philosophy online online as they are free: 

  * [The Art of Unix Usability](http://www.catb.org/~esr/writings/taouu/html/ "Book link")
  * [The Cathedral and the Bazaar](http://www.catb.org/~esr/writings/cathedral-bazaar/ "CatB")

__Linux makes you rich__

  As the 1990's went along we began to see eastablished companies adopting and using Linux. as well as the rise of commercial Linux companies.  Of all the companies that started at that time RedHat Linux is and was the most successful.  Most of all of the Linux distribtions started pre-2003 no longer exist or are not commercially viable.  To illustrate this, today (August 10th 2015) RedHat Linux has a market cap of [~14 billion dollars.](http://ycharts.com/companies/RHT/market_cap "RedHat Market Cap")  

### - The Rise of Commercial Linux and Modern Linux Distros

  As the nature of Linux grew and corporations become more invovled in kernel development, the value proposition of Linux begans to grow as well.  The combination of the Linux kernel and the GNU tools, plus GUI tools became known a Linux distribution - which anyone could freely make.  The shortname became known as a Linux *distro.* Another term to be aware of is a there are different flavors, derivatives, or spins of Linux Distributions. 
  
  After almost 20 years of Linux we can think of the distributions mainly hailing from two distinct families: Debian and RedHat.   There are many other quality distributions of Linux that I don't want to leave out or paint in a bad light.  For the purposes of this book I will focus on the two main distributions.  You can find almost all known  Linux distributions at [http://distrowatch.com](http://distrowatch.com/ "Distro Watch")
  
   *  [Slackware](http://www.slackware.com/info/ "Slackware")
   *  [Gentoo Linux](https://www.gentoo.org/get-started/about/ "Gentoo Linux")
   *  [SUSE Linux](https://en.wikipedia.org/wiki/SUSE_Linux_distributions "SUSE Linux")
   *  [Kali Linux](https://www.kali.org/ "Kali Linux") - Hacking tool based Debian spin
   *  [antiX Linux](http://antix.mepis.org/index.php?title=Main_Page "antiX") - lightwight Debian derivative focused on old machines.
   *  [Arch Linux](https://www.archlinux.org/ "Arch Linux")
   *  [Tails Linux](https://tails.boum.org/ "Tails Linux") - Online security focused Linux distro - debian spin
   *  [LXDE](http://lxle.net/ "LXDE") - lightweight system focusing on reinvigorating older laptops.
   *  and many more... 
  
  __Debian Family__
  
  <a title="By Ilya Schurov , Computerra Weekly (originally posted to Flickr as 9722_00_23_14) [CC BY-SA 2.0 (http://creativecommons.org/licenses/by-sa/2.0)], via Wikimedia Commons" href="https://commons.wikimedia.org/wiki/File%3AIanMurdock.jpg"><img width="256" alt="IanMurdock" src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/3b/IanMurdock.jpg/256px-IanMurdock.jpg"/></a>  
  
 >*"I founded Debian in 1993. Debian was one of the first Linux distributions and also one of the most successful and influential open source projects ever launched. Debian pioneered a number of ideas commonplace today, including employing an open community that allowed (and encouraged!) anyone to contribute (much like how Wikipedia would later operate). And, with its integrated software repositories anyone could contribute to, Debian arguably had the industry’s first (albeit primitive) “App Store”. Today, more than 1,000 people are involved in Debian development, and there are millions of Debian users worldwide."* - [http://ianmurdock.com](http://ianmurdock.com) 

The Debian family contains 3 major sub-families:

![Debian Logo](https://upload.wikimedia.org/wikipedia/commons/thumb/4/4a/Debian-OpenLogo.svg/109px-Debian-OpenLogo.svg.png "Debian Logo")

__Debian Linux__

The Debian distribution (pronounced deb-ian) was founded in 1993 By Ian Murdock and is unique for being one of the only non-commercial company backed Linux.  The current release is Debian 8.1 codenamed Jessie, June 2015.  The Debian project and its history can be found at [http://debian.org](https://www.debian.org/intro/about) and [history of Debian.](https://www.debian.org/doc/manuals/project-history)

There are [currently 128 major Debian based distros](http://distrowatch.com/search.php?ostype=All&category=All&origin=All&basedon=Debian&notbasedon=None&desktop=All&architecture=All&status=Active "Debian based distros") according to distrowatch.com.
 
 These are the main points of Debian and the key I believe to their long term success and usage accross the Linux landscape:
   
   * Initial release scheudle was yearly but as Debian project has grown now is two year release schedule
   * Releases are named after charactrers from the Toy Story movie.  
   * It is the only major distribution not backed by a corporation.  
   * All volunteer project and organization -- project leader is elected on a rotating basis
   * Dedicated to protecting software rights and freedoms of users
   * First major distribution to come with a [Software contract](https://www.debian.org/social_contract "Contract") - of what the project will guarantee to the user.
   * Debian supports free and open source software as superior to closed source but will allow for closed source software/drivers to be installed by the user. 
   * Supported st various times 11 different processor types giving it a wide install base. 

 <a title="By Macguy314 (Own work) [GFDL (http://www.gnu.org/copyleft/fdl.html) or CC BY-SA 3.0 (http://creativecommons.org/licenses/by-sa/3.0)], via Wikimedia Commons" href="https://commons.wikimedia.org/wiki/File%3AUbuntu_logo_copyleft_1.svg"><img width="256" alt="Ubuntu logo copyleft 1" src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/01/Ubuntu_logo_copyleft_1.svg/256px-Ubuntu_logo_copyleft_1.svg.png"/></a>
 
 __Ubuntu__
 
   Ubuntu Linux is a unique distribution.  It is entirely based on Debian.  It is Debian repackaged with a focus on applications "just working."  Around 2004 Mark Shuttleworth, the founder of Ubuntu, was unnerved that Windows had such a domination of the PC market.  He had been a Debian developer, but felt that the partial lack of a corporate sponsor in some ways hindered Debian from catching the marketshare from Windows.  He set out to make a Debian based distro called Ubuntu.  This is a Zulu word for *"community"* as Shuttleworth wanted Linux to be people friendly and work really well out of the box--like Windows.  
   
   By 2004 RedHat, who had owned the desktop Linux market realized that there was little money to be made in that market so they abandoned it decideing to focus on the enterprise market.  This left a void that Ubuntu rushed to fill and they did it well. By 2005, Mark Shuttleworth who had started the Thwate SSL security company which was bought out by Verisign, took his money and invested 10 million dollars in the Ubuntu Foundation to subsidize the creation and maintainance of Ubuntu Linux.  
   
   [Mark Shuttleworth](https://en.wikipedia.org/wiki/Mark_Shuttleworth)
   
   <a title="By Martin Schmitt (cropped by Mary Gardiner) (http://www.flickr.com/photos/foobarbaz/141522112/) [CC BY 2.0 (http://creativecommons.org/licenses/by/2.0)], via Wikimedia Commons" href="https://commons.wikimedia.org/wiki/File%3AMark_Shuttleworth_by_Martin_Schmitt.jpg"><img width="128" alt="Mark Shuttleworth by Martin Schmitt" src="https://upload.wikimedia.org/wikipedia/commons/thumb/7/78/Mark_Shuttleworth_by_Martin_Schmitt.jpg/128px-Mark_Shuttleworth_by_Martin_Schmitt.jpg"/></a>
   
   What made Ubuntu so succesful was tha they forked the opensource work of rock-solid Debian but built on top of it adding in closed source code and user centered features where neccesary in order to make the best experience.  They had business in mind and have indeed captured the desktop Linux market.  But one problem is they haven't found a way to make much money off of their excellent product.  Ubuntu is basically "living" off of the initial 10 million dollar investment of Mark Shuttleworth. Shuttleworth formed a commercial company called [Canonical](http://www.canonical.com/ "Cannonical") was formed to handle commercial support and hires the developers who work on Ubunutu.  
   
   Ubuntu pioneered the idea of rolling releases - releasing every 6 months compared to Microsoft doing 3 to 5 years.  Each distribution is released in late April and late October so there are two distrubutions per year.  Ubuntu also introduced the concept of an LTS, Long Term Support - this means that certain releases will have security pathces, fixes, and software backported to it for 5 years, allowing you to base an enterprise business off of this product and have the stability you need.  These LTS releases happen every even year and in the April distribution.  So Ubuntu 10.04, 12.04, 14.04, 16.04, and so forth. (the first number being the year.)
  
  <a title="By Clement Lefebvre [CC BY 3.0 (http://creativecommons.org/licenses/by/3.0)], via Wikimedia Commons" href="https://commons.wikimedia.org/wiki/File%3ALinux_Mint_logo_and_wordmark.svg"><img width="256" alt="Linux Mint logo and wordmark" src="https://upload.wikimedia.org/wikipedia/commons/thumb/d/dd/Linux_Mint_logo_and_wordmark.svg/256px-Linux_Mint_logo_and_wordmark.svg.png"/></a>
    
__Linux Mint__
    
   Linux Mint started also in 2006 as a fork of the Ubuntu project but with a different desktop interface.  Linux Mint focused foremost on the user and desktop experience out of the box adding multimedia codecs for playback of audio and video directly to the install (see Flash).  Linux Mint is even more user experience focused than Ubuntu and is one of the most popular Ubuntu based distros.

__Devuan Logo Here__

__Devuan Linux__

  [Devuan Linux Project](http://www.devuan.org "Devuan") (Pronounced *Dev-one*) is a fork of the entire Debian project - not just a Debian based distro.  This is a result of a "Debian Civil War" with half of the Debian developers leaving in the Debian project in the beginning of 2015 to begin this distrobution from scratch.  It is a direct fork with fundamental changes to the core operating system.  Other distros change application look and feel but to change the core operating system is a monumental task.  The state of the OS is in late Alpha or early beta as of August 2015 with vm images availalbe for download.  We will talk about this more in detail under the topic "LInux Civil War" later in this chapter. 

   Some of the other notable Debian/Ubuntu based distros are as follows:
   
   *  Lubuntu
   *  Xubuntu 
   *  [Kubuntu](http://www.kubuntu.org/ "Kubuntu") Uubntu remixed with the KDE desktop Environemnt
   *  [SteamOS](http://store.steampowered.com/steamos "SteamOS") Steam onlien gaming companies official Linux distro
   *  [Kylin Linux](http://distrowatch.com/ubuntukylin "Kylin Linux") Ubuntu Distro designed for Mandarin Chinese as opposed to English.
   *  [Raspian])http://www.raspbian.org/ "Raspian") This is a Debian based distro that is standard recommeded for the Raspberry Pi.
   *  [gNewSense](http://gnewsense.org "gNewSense") <- GNU/Linux FSF recommended distro, entirely GPL compliant software.

  __RedHat Family__
  
  ![RHEL](https://upload.wikimedia.org/wikipedia/en/thumb/6/6c/RedHat.svg/93px-RedHat.svg.png) 
  
  RedHat Linux was formed shortly after teh Debian project launched in 1995 Marc Ewing and Bob Young.  It was one of the first commercial Linux companies and one of the few to survive to the modern day independant of an existing company.  RedHat source code is currently shared accross three main distributions: Fedora, RHEL (RedHat Enterprise Linux), and CentOS.   
  
   You can read more about RedHat from their website:
   
  *  [About](http://www.redhat.com/en/about/company)
  *  [Red Hat History](http://www.redhat.com/infographics/corporate/data/ "RedHat History")
  
  <a title="See page for author [Public domain], via Wikimedia Commons" href="https://commons.wikimedia.org/wiki/File%3AFedora_logo_and_wordmark.svg"><img width="256" alt="Fedora logo and wordmark" src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/09/Fedora_logo_and_wordmark.svg/256px-Fedora_logo_and_wordmark.svg.png"/></a> 

   [Fedora Project](https://getfedora.org/ "Get Fedora")
  
   The [Fedora Project](https://en.wikipedia.org/wiki/Fedora_Project "Fedora Project") was started in 2003 when the Red Hat Desktop Linux product was merged with the comapny/community based spin off Fedora Core Linux.  The Fedora project's focus was rapid development and rapid release.  They would release two distributions almost yearly, with package and update support only extending back to the previous version cutting off support to viable but from Red Hat's point of view outdated software.  Remember their focus was rapid iteration of the project to quickly test new technologies.  
   
   For example Fedora 22 was released on XYZ date, Fedora 21 was released ABC, and Fedora 20 was released DDD but is not suppoprted anymore - even though it was only realed a short while ago! Why so fast and so merciless on not supporting older versions?  With this concept they would not have to without having to worry about legacy applications.  This distribution was meant for desktop users and developers who don't mind updating rapidly.  The reason for this iteration is that the Fedora Project is really jsut a testing ground for technology that will eventually go into Red Hat's enterprise project, referred to as RHEL.    
   
   Currently there are [25 Fedora based distros](http://distrowatch.com/search.php?ostype=All&category=All&origin=All&basedon=Fedora&notbasedon=None&desktop=All&architecture=All&package=All&status=Active) or Fedora calls them *"spins"* -- this term is unique to Fedora.
  
![RHEL](https://upload.wikimedia.org/wikipedia/en/thumb/6/6c/RedHat.svg/93px-RedHat.svg.png)
  
   __RHEL__ 
  
  RedHat began to see the opportunity to create a Linux distro targeting enterprises and make money using opensource at the time.  A big market that was practically cornered by two companies were Java based applications and database servers - MySQL or Orcale.  These markets had been the domain of Sun and its Unix based Solaris Operating System for years, as well as Microsoft runnning Oracle on Windows.  RHEL could enter that market, running the same applications, and do it on cheaper Intel x86 based boxes.  With Oracle announcing it would port its products to RHEL, this platform became to the go to choice as the alternative against Microsoft and helped put Sun and Solaris basically out of business.  The acronym stands for RedHat Enterprise Linux.  

  The key to RHEL's success in the enterprise is its long term stasbility.  Much like the version of Windows Servers it competes with - the applciation platform is expected to run for 5+ years.  A enterprise grade server product cannot be changing every six months like the Fedora project.  RedHat instead takes "snapshots" from Fedora and freezes them in time.  As of today (August 13th 2015) the current version of RHEL is 7.1 which is a freeze of the technology point in Fedora 19, whihc was released July of 2013.  This way the developers get to know the platform and software versions that will be maintained and supported long term. How succesful is this strategy? By 2012 they became the first Linux based company to make a billion dollars in a physical year.  But this success brought about a serious opensource question, if you have a successful prodcut like RHEL, since you are using GPL based opensource code--you have to opensource your code--that means anyone else can redistribute your code freely, in theory eating your lunch.     
  
  <a title="By CentOS Project (http://wiki.centos.org/ArtWork/Logo/Type) [GPL (http://www.gnu.org/licenses/gpl.html) or Public domain], via Wikimedia Commons" href="https://commons.wikimedia.org/wiki/File%3ACentOS_Logotype.png"><img width="256" alt="CentOS Logotype" src="https://upload.wikimedia.org/wikipedia/commons/8/87/CentOS_Logotype.png"/></a>
  
  __Centos__
    
  By 2004 many people began to see the utility and success of RedHat Linux, and being opensource they began to fork the code and make their own distributions.  CentOS is one of them.  By 2010 they emerged as one of the two remaining RHEL derivatives.  Their developers, like Debian, are entirely volunteer based and not backed by a company.  Their motive was to take the solidness of RHEL and just update a few features and add more modern software packages sooner then the 5 year RHEL cycle.   Initially RedHat didn't support CentOS--taking them to court numerous times, as CentOS had not removed all of RedHat's trademarked logos in all the code.  Eventually all of RedHat's copyrighted material was removed and CentOS has a leagal copy of RHEL to redistribute and use.  This made RedHat angry as they were loosing sales to enterprises using CentOS insteaf of RHEL.  By 2014, RedHat and Centos came to terms to work together--with RedHat offering to sell support contracts to CentOS users.  Is CentOS doing anything illegal?  Not according to the GPL and the spirit of opensource, but it does bring up the financial issue again.
   
  __Oracle Linux__
    
  [Oracle Linux](https://en.wikipedia.org/wiki/Oracle_Linux "Oracle Linux")
  
  Did you think that Oracle would allow their logo to be displayed under an open license? Not to be out done.  Oracle who saw that many of their customers were paying RedHat for operating systems licenses, buying support contracts, and then running their database on top of it wanted a piece of the action.  Oracle now owns Java--which is the primary tool used to interface with all the Oracle and its suppoprting products.  Oracle made a fork of RHEL's opensource code and placed their logos, Oracle specific tools, and made their own software tweaks in this fork and called it Oracle Linux.
  
 [Oracle Linux](https://en.wikipedia.org/wiki/Oracle_Linux) was born in 2007 and is a fully GPL compliant OS.  Oracle claims that their *"Unbreakable Enterprise Kernel"* is fully compatible with RHEL, and that Oracle middleware and third-party RHEL-certified applications can install and run unchanged. One may ask, isn't this illegal? Is Oracle breaking the law?  Not according to the GPL - they are fully entitled to do this and thus compete with Red Hat selling support contracts on Red Hat's created software--this is the nature of the GPL license.   
  
  __Unix and the BSD Family__
  
  While Linux was exploding in the mid 1990's the AT&T lawsuit against BSD had been settled and work could resume of the BSD forks of Unix.  Unfortunately the BSD code splintered into 4 main distros pulling the already thin developer group that hadn't shifted to Linux development, even thinner. 
  
   ![FreeBSD](https://upload.wikimedia.org/wikipedia/en/thumb/d/df/Freebsd_logo.svg/320px-Freebsd_logo.svg.png)
   
   * Released in November 1994
   * Essentially the inheriter of the BSD code base and the largest BSD implementation.  
   * Leagally prohibitted from using the term *"Unix"* as outcome of AT&T lawsuit.
   
   ![DragonFly BSD](http://www.dragonflybsd.org/images/FullLogo.gif)
   
   * Fork of FreeBSD in April of 2005 by Matthew Dillon.
   * Focused on unique techniques in handling mutliprocessing in the FreeBSD kernel
   * Introduced a new filesystem called HAMMER and HAMMER2

   __PC-BSD__
   *  FreeBSD based distro with a focus on user interface and experience. 
   *  Provides friendly installers and package managers for users 

  __Ghost BSD__
  *  Does something...

   ![NetBSD](https://upload.wikimedia.org/wikipedia/en/thumb/5/5c/NetBSD.svg/307px-NetBSD.svg.png) 
   
   * Released October of 1994 as another version of the BSD code after the lawsuit.
   * Focuses on portability to run this OS on nearly every platform you can think of.
   
   ![OpenBSD](https://upload.wikimedia.org/wikipedia/en/thumb/8/83/OpenBSD_Logo_-_Cartoon_Puffy_with_textual_logo_below.svg/320px-OpenBSD_Logo_-_Cartoon_Puffy_with_textual_logo_below.svg.png) 

   * Fork of NetBSD lead by Theo de Raadt end of 1995
   * Founded by Theo de Raadt
   * Theo was banned from NetBSD in 1994.
   * He complained that they were developing too slow and not focusing on security.
   * OpenSSH comes out of this project.
     + [Microsoft recently became the first "gold sponsor" of the project](http://undeadly.org/cgi?action=article&sid=20150708134520)
     + Recognizing the standard of SSH (secure shell) they are moving to port and integrate SSH natively to Windows. 
   * Project is focused on radical implementations of security and safe coding practices--leveraging itself as the most sercure OS.
   
   [Minix 3](https://en.wikipedia.org/wiki/MINIX_3 "Minix 3") 
   
   * Released October of 2005 
   * Since then the OS went from a teaching tool to a product being used commercially.  
   * Began using NetBSD user space applications to give it a GUI and make it a viable commercial product. 
        
   __Open Solaris / Open Indiana / Smart OS__
   
   <a title="By openindiana.org [Public domain], via Wikimedia Commons" href="https://commons.wikimedia.org/wiki/File%3AOpenIndiana_logo_large.svg"><img width="256" alt="OpenIndiana logo large" src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/e7/OpenIndiana_logo_large.svg/256px-OpenIndiana_logo_large.svg.png"/></a>
     
   Open Solaris
     
   <a title="By Sun Microsystems (OpenSolaris) [GFDL (http://www.gnu.org/copyleft/fdl.html) or CC-BY-SA-3.0 (http://creativecommons.org/licenses/by-sa/3.0/)], via Wikimedia Commons" href="https://commons.wikimedia.org/wiki/File%3AOpenSolaris_Logo.svg"><img width="128" alt="OpenSolaris Logo" src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/2c/OpenSolaris_Logo.svg/128px-OpenSolaris_Logo.svg.png"/></a>
   
   Joyent  
   
   <a title="By Joylent (uploaded by (Lamro@enwiki) [Public domain], via Wikimedia Commons" href="https://commons.wikimedia.org/wiki/File%3AJoyent-logo.png"><img width="256" alt="Joyent-logo" src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/96/Joyent-logo.png/256px-Joyent-logo.png"/></a>
   
   [SmartOS](https://smartos.org/ "SmartOS")
   
   * In 2006 Sun had experiemented with creating and opensource user based distro from their Unix based Solaris OS
   * They hired Ian Murdock (the guy who started Debian) to oversee this project
   * Project was called Open Solaris but was killed when Oracle purchased Sun in 200X
   * The resulting codebased was forked and turned into a project called Lumios
   * Currently their is a competing Open Solaris based distro called Smart OS which is produced by Joyent 
     + Combines the best of the BSD underpinnings but runs the best of Linux based desktop applications and software
        
### - Impending Linux Civil War

<a title="By Kushal Das (Own work) [CC BY-SA 3.0 (http://creativecommons.org/licenses/by-sa/3.0)], via Wikimedia Commons" href="https://commons.wikimedia.org/wiki/File%3ALennart_poettering.jpg"><img width="256" alt="Lennart poettering" src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/30/Lennart_poettering.jpg/256px-Lennart_poettering.jpg"/></a>

__Lennart Poettering__

  Not since Linux Torvalds has a man been so loved or reviled in the Linux community.  Lennart is a name you need to know as well.  He is currently a developer for Red Hat and having worked on many open source proejcts.  His current project is systemd.  Systemd is a replacement for the traditional SysVInit program that started all of the Operating Systems process upon boot.  
  
  Poeterring has angered many people by breaking certain Unix traditions and conventions in the name of speed and features.  The Unix philosophy of having little programs do one thing well goes right out the window. Poetering argues that philosophy is a byproduct of an era where computing was slow and disk space was precious.  If Linux wants to be taken serious like Mac and Windows--it needs to think like Mac and Windows.  Poeterring is young and wants to push the development of the operating system of Linux forward rapidly.  
  
  The other major point of contention is with all the changes in systemd to the boot process, many other pieces of software need to change as well.  Linux has always been about choice but the GNOME desktop developers have chosen to hard integrate with systemd. Meaning that if you operating system uses systemd instead of SysVInit - then you m,ay very well in the future be forced to use GNOME as it will become a dependency of your init system.
  
  This leads to an interesting point.  All major distros have moved to systemd.  Debian was the last hold out and they actually had a civil war and split over this issue.  Half of the developers left and went to form a distro called Devuan--which is focusing on removing all the systemd dependencies and putting choice back in the users hand.
  
  Systemd has many nice and needed features.  Leonart is updating pieces of Linux that haven't been touched in ages. He even wrote a [21 part defence](http://0pointer.de/blog/projects/systemd-for-admins-1.html "21") of systemd on his website. I will talk more on the technical aspects of systemd in the chapter X.
     
  The fears of Linux users are that systemd will grab dependencies and eventually force Linux users into a small sub-section of systemd supported software choices.  In a sense create a vendor lock in.  What makes this all the more intreguing is that Lennart works for Red Hat.  Would Red Hat mind if this systemd technology improved the Linux experience at the cost of choice of software and freedom available to the user?  That is a good question.  This also begs the question - can Linux survive as an independant and open software or does it need a commercial comapny backing it?  Or could this be seen as Red Hat's grab for the entire Linux market?  It is too early to tell but keep a watch on what happens with systemd.

## - Chapter Conclusion and Summary

  Wow - we covered a lot of history -- but it is important to the understand the current state of Linux usage.
  [Learn more about opensource licensing](http://www.openlogic.com/resources/enterprise-blog/archive/open-source-license-interpretation-made-easy)

   [Additional Reading on the Unix history side](http://www.oreilly.com/openbook/opensources/book/kirkmck.html "History of Unix")

### - Review Questions

Get into groups and answer/discuss these questions

Based on the movie's tone - why would you think there is a definate anti-microsoft tone?

Would Richard Stallman enter into a discussion on which is a better product: Microsoft Word or LibreOffice Writer? Why or why not?

Would Eric S. Raymond enter into a discussion on which is a better product: Microsoft Word or LibreOffice Writer? Why or why not?

Why did Bruce Perens help write the Open Source Definition / Debian Social Contract Standard?

What were the two commercial Linux companies featured in the movie?

What is RedHat Linux's stock price today?

What is VA Linux's stock price today?

How does Ricahrd Stallman react at the end of the movie of the success of the Linux kernel to the exclusion of the GNU tools?

### - Podcast Questions

[Listen or watch](http://twit.tv/floss/73) this podcast - http://twit.tv/floss/73

 *  Who is Tim Orielly? ~3:00-5:00
 *  What is Oscon? ~6:45
 *  Who coined the term web 2.0? ~13:34
 *  What did we learn from the IBM PC? ~18:30
 *  What is web 2.0? ~19:30
 *  Open Source vs Open Data - what does Tim Orielly think is the ultimate destination for computing? ~23:00
 *  Where is the money made in open source - software or data? ~ 34:00
 *  What prediction did Tim Oreilly make in this podcast (2009) that is now coming true? ~51:32
 *  [radar.oreilly.com](http://radar.oreilly.com) What is the lag time from articles on this site to the main stream media? ~55:00

### - Lab

[Watch Revolution OS - https://www.youtube.com/watch?v=jw8K460vx1c](https://www.youtube.com/watch?v=jw8K460vx1c) and answer the questions listed under review questions.





