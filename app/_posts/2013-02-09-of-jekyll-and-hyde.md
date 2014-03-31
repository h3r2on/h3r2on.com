---
date: 2013-02-09
layout: post
title: Of Jekyll and Hyde
slug: of-jekyll-and-hyde
comments: true
categories:
- web
- opinion
tags:
- jekyll
- inuit.css
- compass
- github
---

For the last two years or so I've been using [SquareSpace](http://squarespace.com) as my host and CMS. Hands down, they have the best customer support and SquareSpace 6 is an amazing platform for both easy site setup and their new developers stack is really well thought-out.
My one issue is they choose LESS, and while a fine pre-processor, I've chosen SASS/Compass and don't plan on changing any time soon.
So for my site redesign I've decided to move from Squarespace to GitHub Pages. I have to say it's really refreshing to completely build a site from scratch again, as opposed to working with a more structured CMS. For this design my toolkit is HTML5 Boilerplate, inuit.css library and I invited Compass to the party to provide some additional CSS3 mixins.
I picked [inuit.css](http://inuitcss.com) because I've been an OOCSS proponent for quite a while and [@csswizardry](http://csswizardry.com) has built a great library that does it's best to not influence your design choices like other library/frameworks and IMO delivers on that promise.
I picked HTML5 Boilerplate as my HTML starting point for many reasons, most of which I detail in [this earlier post]({% post_url 2012-03-03-bootstrap-and-h5bp %}).
In adding Compass to the stack I've modified a few of the inuit.css mixins to use the helpers and function builtin to Compass. 
The most interesting thing I'm attempting in this build is to use just `<nav>` and a elements for all navigation blocks. So my main nav looks like this:

    <nav class="nav site-nav">
      <a class="site-nav__blog" href="/">blog</a>
      <a class="site-nav__about" href="/about/">about</a>
      <a class="site-nav__projects" href="/projects/">projects</a>
    </nav>

To get this to work I've rewritten the nav and pagination classes of Inuit to require `<nav>` instead of the `<ol>` or `<ul>` elements. My next task is wire up a deeper navigation structure. Credit for this idea goes to [@bphogan](http://twitter.com/bphogan/) for his tweet, thinking out loud if it could reasonably be done. 

My fork of inuit.css can be found here [h3r2on/inuit.css](https://github.com/h3r2on/inuit.css).