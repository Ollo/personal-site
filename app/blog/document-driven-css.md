---
title: document driven css
date: 2016-05-20 10:28:00
tags:
  - blog
  - css
  - architecture
  - web development
---


As I've worked with several different teams over the years I've found documentation to be a bit of a hot button topic. Some feel over documentation is the only way to professionally deliver work and some prefer to simply write "self-documenting" code. I've sat through multiple debates and have been part to many a code review where these two mindsets have caused quite a stir.

#### Premise

On a recent fairly large application build I decided to test some theories around documentation with Sass. I wanted to attempt a documentation driven approach which I define as:

> All code that is intended for re-use or extensibility within a library or project should have documentation written up-front or in parallel instead of it being added after the fact.

This may at first just appear to be a pedantic argument, but I wanted to research and possibly prove a couple of hypotheses through this approach.

1.) The project at the end wouldn't lack documentation like so many other great projects do and if the documentation efforts had fallen behind it would be less effort to back fill.

2.) Code quality would increase as there was more thought put into the solution at the time of authorship.

In my opinion CSS is a fairly simple language with a long history of hacks. I find its very easy and far to common to just write more code rather than think through problems up front and write well thought out modular solutions. Also documentation as a practice is pretty rare in CSS as a whole unless you are viewing the source for a popular public framework or library.

#### Risks

Alongside these hopeful outcomes I also theorized a couple potential side-effects of taking this approach.

1.) Developers velocity would decrease as more thought would be needed during authoring and this might disrupt a typical workflow.

2.) Code bloat. I wondered if writing docs upfront would influence a developer into thinking every line of CSS has to be modular and re-usable.

I feel these risks have to be weighted differently depending on the project. In my test case above, we had plenty of runway to work through some early prototypes and think of systems to use in our css. These fairly complex systems necessitated a comprehensive set of accompanying documentation that other engineers could ingest for feature development. If I had a smaller site or project I doubt I would take such a stern approach to being document driven.

#### Tools

[KSS](http://warpspire.com/kss/) is the tool I decided to use for documentation. It had some notable use cases and pretty decent documentation even if it only provided ruby references. I also utilized a [gulp plugin](https://www.npmjs.com/package/gulp-kss) to automate this step into our existing build pipeline. We also created our own theme for our documentation and incorporated angular and google material as both of those libraries are used in the project and they were needed as dependencies in order to properly represent our apps components.

#### Conclusion

If I told you this experiment went off without a hitch I would be lying. We did end up having a much larger and more comprehensive set of documentation, but when deadlines loomed we loosened our convictions to maintain them. We ended up having to backfill documentation and do several rounds of refactoring to get our Sass components and docs up to date after major deadline pushes with new feature development. The documentation did however prove to be a useful resource to more team members that were more focused on data and application development with less focus on UI. Overall I feel that for this strategy to be successful it needs to be established as a core principle for each team and there really needs to be buy in from the whole team to ensure success.
