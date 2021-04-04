---
title: "Getting into rem's for responsive typography"
tags:
  - blog
  - css
  - sass
  - web development
date: 2014-01-10 15:51:22
---

So for the past few months I have been using Sass for all of my projects.  I've been using Bourbon and Bourbon Neat as part of my workflow but recently have been working to implement rem measurements for my typography to assist in font scaling for responsive builds. This was a bit daunting at first after I read about the calculation for [rems](http://gregrickaby.com/using-the-golden-ratio-and-rems/) as I was already used to being spoiled by Bourbon's `em()` function so I whipped up a function to do the conversion for me.


    // calculate rem based on a pixel value
    @function rem($value, $fontbase: 10) {
      @return($value / $fontbase) * 1.0rem;
    }

    .rem_test {
      font-size: rem(40); // 40px == 4rem
    }


Hope you find this helpful.  
