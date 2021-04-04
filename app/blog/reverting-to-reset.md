---
title: reverting to reset
date: 2016-03-22 13:39:58
tags:
  - blog
  - css
---

I love approaching projects from a modular, componentized approach and commonly am looking for new tools or techniques across languages to facilitate this methodology.

Today I was reading an [interesting post](http://thesassway.com/advanced/modular-css-typography) on making css typography more modular and came across a thought provoking statement on the authors rationale on using a css reset over something like Normalize.

> The other reason to start with a fuller reset is that starting from zero allows you to layer on styles without worrying about turning off other styles. Read that one more time. Anytime you have to turn off styles in multiple places in your stylesheets your are spreading the knowledge of those styles throughout your stylesheet instead of having them in only one place.

This is interesting for me since a couple years back I switched from using Eric Meyers reset to using Normalize so I could focus more on the unique UI components of an application from a sensible baseline instead of having to start from ground zero.

 Reflecting on some of these projects now however, I can 100% see how that mindset / approach can totally backfire and make truly modular code difficult. Typically this has manifested for me any time I needed to refactor a component from being view / feature specific to something more useful to the application globally. I seem to find that the cascade from parent components or default styles are coupling the component and thus quite a bit of css needs to be refactored.

 On my next project I think I'll try switching back to a reset and see if this assists in better flexibility.
