---
title: The Perfect Linux Desktop Setup for Web Development
tags:
  - blog
  - linux
  - open source
  - web development
date: 2010-08-26 19:55:36
---

As a fellow open source enthusiast and web developer, [Josh](http://ollomedia.com/author/administrator/) has been kind enough to invite me to guest post on one of my favorite topics: Linux-based web development. I specialize in the development end and less on design, so bear that in mind, though I'll also introduce some graphic design tools as well. While the linux platform still lacks a native port for Adobe CreativeSuite, to the chagrine of Linux-loving web developers everywhere,  there are still plenty of stunningly useful tools for web developers working on Linux. Before  I get to a summary of my favorite of these tools though, I'd like to take a second to talk about the importance of open source in the web industry.

<!--more-->

As web developers, we benefit immensely from the richness of the open source community, from the profligate offerings for code libraries for front-end development (YUI, MooTools, jQuery),  the scripting languages we love (PHP, JavaScript, Python, HTML, XHTML), the very platform that powers most of our servers (Linux, Unix, BSD), to the servers that offer up our creations for consumption (Apache, Nginx, Lighttpd, Tomcat).

Without the generous contribution of labor and creative product by the multitude of developers working on this great software, the modern web might have a very different face; it's very difficult to imagine that without the multitude of freely available solutions, the web would be as accessible as it is today.

My heartfelt thanks goes out to the people who make this possible, including the corporations that stand behind open source, putting their money where their mouths  are in paying for open source developers and defending open source licensing in the courts. With that said, let's look at some of the open source tools for facilitating the web development workflow on the Linux desktop.

### Graphics

#### [Gimp](http://www.gimp.org/ "GIMP is the GNU Image Manipulation Program")

An ever-popular, multi-platform image editing tool, Gimp offers a host of tools useful to web developers. Aside from the obvious utility in graphic design for logos, buttons, icons, etc. Gimp also offers tools for splicing an image into pieces and generating table code for layout. This obviously pairs well with web design, as a website layout can be designed as a single graphic, then sliced into it's composite parts. Gimp also has a handy feature for optimizing images for the web, reducing file-size and improving load-times. With Gimp's plugin architecture, there are many additional ways to expand the basic capabilities to fit Gimp into your work-flow.

#### [Agave](http://home.gna.org/colorscheme/)

This simple, lightweight application for the GNOME desktop offers web developers a simple way to generate complementary colors for website elements, offering color pairs, triads, tetrads, etc. with on-demand color-matching and saturation/tone adjustments. It very conveniently provides the corresponding color codes in several formats (RGB/Hex), and the ability to save a list of your favorite color-schemes.

#### [Synfig](http://synfig.org/)

This remarkably powerful 2d animation studio is built from the ground up to offer industry quality animation capabilities in a convenient way. Developed by an industry professional who was tired of working with inferior tools, Synfig offers the best flash development capabilities found anywhere, native to Linux. Though I personally avoid flash wherever possible, it remains a reality for web developers, and Synfig more than adequately fills the need.

#### [Inkscape](http://www.inkscape.org/)

An incredibly popular tool for vector graphics, Inkscape offers full-featured vector design and editing capabilities, and works very well for designing flexible website layouts that export well for optimization and post-processing in Gimp.

### Coding

Every developer's idea of a useful coding environment differ based on purpose, experience and need. Some prefer the no-bull text-edit mode of vim, emacs, gedit, or kate, some may prefer a fully gui editor like Kompozer, and most probably fall somewhere in between, I'll give a brief overview of one or two tools for each preference below.

#### [Kompozer](http://kompozer.net/)

A long time favorite, Kompozer is a simple-to-use web editor that offers a fully graphical development environment with great support for css based templates, great built in code libraries and fully standards compliant code generation. With easy switching between graphical and source-view, this web development software is an understandable favorite for many beginning web developers and a trusted familiar for experienced developers.

**Key features:** _gui and source editing, built in code support and easy css template generation, built-in ftp client.

#### [Bluefish](http://bluefish.openoffice.nl/)

My personal favorite development tool, Bluefish has the perfect mix of useful development tools and configurability in a lightweight gtk+ interface. With auto-completion of html, php, and css tags/attributes, a ready css template generator, configurable syntax highlighting, find and replace functionality, it offers all the frills for the text-friendly web developer. To cap off this handbag of win, Bluefish offers a best-of-class image insertion dialog, with automatic thumbnail generation and automatic linking of the thumbnail with the original image, making gallery generation a cinch.

**_Key Features:_** tag auto-completion, configurable syntax highlighting, css template generation dialog, automatic thumb-nailing, complete php reference guide

#### [Quanta Plus](http://quanta.kdewebdev.org/)

One of the best interfaces and offering reliable stability (everyone hates a crash that causes the loss of hours of work), Quanta Plus is a very nice development environment, with a fully graphical, fully code, and split-view development interface, so that you can watch your code unfold as you lay it down.

This tool is very useful, but there are a couple of downsides. First: being developed strictly for the KDE environment, Quanta drags in a _ton_ of KDE dependencies when installed on the GNOME desktop. If you use KDE anyways, this is clearly not a problem, but as GNOME has the majority of installs, for most Linux users, Quanta may not be worth the extra libraries and more frequent updates for software you only use for one application.

Second: Quanta development seems to have come to a standstill, with the last stable version released in 2007\. This is disappointing, as the developers produced a high quality application that I for one would have liked to see continue to evolve.

**Key Features:** _syntax highlighting, Graphical/Source split-view, support for css generation, project management, multi-language support, easy web template management across and within projects_

**Honorable Mentions:** Though I'm fond of the above applications for their ease of use and excellent feature sets, many developers prefer other applications, and two that have quite enthusiastic user bases are **_Screem_** and **_Geany_**.  If none of the above strikes your fancy, these may be what you're looking for. :)

#### Integrated Development Environments

IDE's offer a variety of advantages to web developers, aiming to provide all the tools necessary for web development in a central application. Common features are project management, multi-language support, in-application publishing, debugging and revision control. Though there are many IDE's for many different programming purposes in Linux, I'll merely list a couple of the larger, more feature-rich applications.

#### [Aptana](http://www.aptana.com/)

Probably my favorite IDE when I am in the mood for a feature-rich, java-script aware environment, Aptana, based on Eclipse, packs a lot of features into a convenient, fast application for web development. Probably the best feature in Aptana is the large collection of importable plugins that let the developer add support for all kinds of projects. By far the most generally useful plugins are the code libraries, including jQuery, YUI, Mootools, Prototype and many more. For each library, code assistance, sample projects and documentation is brought directly into the application. Another big feature is the built-in JavaScript debugging utility. The Aptana team is working on Aptana 3, which will feature git support!

#### [Komodo](http://www.activestate.com/komodo-edit)

The first IDE that ever managed to hold my attention, Komodo is absolutely fantastic for PHP developers, offering excellent syntax assistance, code history (fwd/backwd movement through code), and best-in-class code repository management. It includes the ability to checkout code from central repositories directly within the IDE, and built in support for all of the major revision control systems (git, bzr, mercurial(hg)). Komodo also features an extensively configurable interface, with support for multiple, paned top-level windows for simultaneous review and editing of multiple files. As someone who primarily works in PHP, Komodo is the most useful application for most of my work-flow.

### Crash/Performance Testing

Every developer knows that sometimes, despite your most thorough review, bugs can crop up when a site goes live, and it's critically important to be able to test an application before it's put into production. For HTML, CSS and simple JavaScript projects, testing can be done readily within the browser by previewing local files, but if you plan to use any PHP, Perl, or Python in your application, you simply can't presume that the functional bits of code will behave as you expect without putting them through rigorous testing.

To that end, Linux easily outshines other development platforms, especially in the popular combination of tools known as a LAMP server. If you're not already familiar with the term, LAMP stands for Linux, Apache, MySQL, PHP, who, when the power of their rings unites, provides a powerful, stable, and flexible platform for almost all web-development needs, including a highly stable, configurable OS with low overhead, to get the best performance out of the available hardware, a powerful, secure and extensible web server, MySQL for database needs, and PHP for dynamic scripting, file uploads/downloads, and database interaction.

The tremendous news to Linux using web developers, is that you're already using the base of this killer combination. Every major distribution provides a simple-to-install binary package for Apache, MySQL and PHP which will typically be configured to run right out of the box. Many distributions even provide a metapackage to install the LAMP package as a whole without seeking out the individual binaries. While the availability of Apache for easy installation is terrific, if you happen to develop on older hardware, a netbook, or would just rather not add another service to your desktop, the [XAMPP](http://www.apachefriends.org/en/xampp.html) project is a terrific solution for pre-configured, fully featured testing environment for web developers which includes Apache, MySQL, PHP and Perl as well as  several demo projects to demonstrate various functionalities, and phpMyAdmin for a friendly database interface if you're not comfortable at the command line.

### Conclusion

The Linux desktop truly offers a broad variety of options for web developers who may be tired of keeping around a dual boot for a smattering of tools with no familiar counterparts on their desktop of choice. I hope to have introduced here a collection of tools that will help other web developers to make the leap to a fully open source development environment, with no loss of critical features, and minimal workflow adjustment.

Though it would have been impossible to review all of the possible applications for web development available on Linux, if I left out something you consider critical to your workflow, please let us know in the comments, we'd love to hear about your favorite web-dev workflow applications. Did we leave out a particular part of your workflow? Still not sure what may be available to meet a particular development need? Feel free to ask, we'll be glad to try to help!
