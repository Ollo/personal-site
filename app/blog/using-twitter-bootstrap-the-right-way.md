---
title: Using Twitter Bootstrap the right way
tags:
  - blog
  - css
  - less
  - web development
date: 2012-10-12 13:26:55
---

So if you haven't jumped into bootstrap to speed up front end development or at least explored it you need to, and hopefully this writeup taken from some of my successes and failures will help jumpstart you into using it effectively as
a front end scaffold.

### First we need to understand that Bootstrap is a framework..

One of my first mistakes was in not really understanding what this means and customizing its core directly. This mistake has caused numerous problems like being stuck with an older version and working way harder to override its css output :(

After the first couple of projects I found that the only way to use it effectively is to build off of it and not customize its core files directly. This concept is similar to other platforms and libraries I use { jQuery or WordPress } but it didn't occur to me immediately since it was a front end framework and the early documentation guided users to work off of the variables to customize it. This caused me plenty of problems until I found the below approach.

## Setup

### Download the full source from Github { the LESS version }

[https://github.com/twitter/bootstrap](https://github.com/twitter/bootstrap) This is the full core of the framework. It will take some learning if your not already using LESS but it shows how the features are truly built. If you haven't already viewed bootstrap like this take some time and examine the files and learn which features are created through each file, there are quite a few and learning where they are defined will help later when you want to build off of them or over-ride their look and feel.

### Get the right tools

I use a compiler which took some time to getting used to as a front end guy who's previous experience with compilers was [Dev C++](http://www.bloodshed.net/devcpp.html) in an intro CS class. I've come to find with a little flexibility in my workflow it speeds things up and can help with debugging as I'm adapting to using LESS instead of just CSS. I currently use [CodeKit](http://incident57.com/codekit/) which offers some cool js and framework support. It is a paid app so if your just getting started you might want to try some of the free options { [LESS for Mac](http://incident57.com/less/), [WinLess](http://winless.org/) ( ironic ), [Simpless](http://wearekiss.com/simpless), or [Crunch](http://crunchapp.net/). }

### Set up your development project

Recently at WordCamp here in St. Louis I discussed theme development best practices and one of the concepts I covered was abstraction. The concept holds true in the method I use to work with bootstrap which I find to work really well. I start with a basic project folder for the site name or project I'm working on and create the basic folder structure for the types of files I will be using. I also add a folder called bootstrap to contain the frameworks less files.

Now I copy over the files from bootstrap that I downloaded from Github into the appropriate directories minus the tests folders that were used in development. Now I have a clean folder structure with some basic assets to start using on my project.

### Getting started

Now that you have a basic site structure lets set up our compiler with some resources and instructions on how to produce our styles. First inside of our less folder lets create some .less files to tell the compiler what we are working with. I start with a

* `style.less` { the master file },
* `layout.less` { general layout },
* `theme.less` { colors, buttons, etc }
* `typography.less` { for headings and type faces }
* `misc.less` for mixins and utility classes.

Once these files are created open your `style.less` file and add the following lines.

    /* my new bootstrap site */

    @import "../bootstrap/bootstrap.less";
    @import "../bootstrap/responsive.less";

    // import your unique less files as you build

    @import "layout.less";
    @import "theme.less";
    @import "typography.less";
    @import "misc.less"  // mixins etc

Once you have created these files and this structure you can open your compiler of choice and add your new project. In CodeKit you simply click the (+) plus sign and browse for your site folder. Once you have chosen this lets modify the compiler behavior.

Basically we want to make sure it is detecting the import statements and that it is only compiling the single style.less file. Also if it doesn't automatically set the output path for the compiled css you will want to right click and tell it to use /css/style.css. Now we can get started on building our new site with less and the power of bootstrap so if your not already confused read on.

### File Strategy

I mentioned before that one of the key things I've learned as a developer is abstraction. This concept is constantly at the back of my mind when I'm working on a project because I find its the best way to build readable clean code that someone else may have to work on down the road after I'm finished working on a project. When I set up my less folder with those basic files in the previous step its just a starting point. As I get further into a site I will create several more less files and import them into the style.less file so they are compiled into the final css. This maintains clean easy pieces in my code that are easy to digest.

I also heavily comment using less comments `//` as they don't end up in the css and are a courteous way to document my train of thought as I'm working on a layout.

> **_The key thing is to not be afraid of files._**

With this method and less they are compiled into one css file so your not adding a bunch of extra http calls and damaging your sites load time by keeping everything broken out and readable. You can even take optimization a step further when your ready to put your site into production and only import the bootstrap files that actually pertain to your design.

**_Wait.. what ?_**

Yes. If you open the bootstrap.less file from the framework you'll see they are doing the same thing with import statements so you can lower the end size of your css file by only pulling what you need!

### Closing

This has taken a couple of months for me to refine and get comfortable with but now I'm finally starting to see the benefits as I work with a team of developers on larger projects. This organization lets us minimize development time and makes our code easier to understand without lots of instruction and I hope it helps you on your development projects in the future. If you see improvements that can be made I'd love to hear your feedback or findings while you experiment.

Happy coding.
