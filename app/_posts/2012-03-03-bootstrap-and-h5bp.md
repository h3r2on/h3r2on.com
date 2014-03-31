---
date: 2012-03-03
layout: post
title: 'Bootstrap &amp; HTML5 Boilerplate'
slug: bootstrap-and-h5bp
categories:
- web
tags:
- bootstrap
- HTML5
- H5BP
- boilerplate
- frameworks
---

I've never been a big fan of frameworks they never fit into my design pattern and how I like to work. Recently though I've begun to retool my base toolkit and I wanted to see if one of the these would work for me, so I used two new projects at work as guinea pigs to try out HTML5 Boilerplate and Twitter's Bootstrap. Here's what I found.
##[HTML5 Boilerplate](a href="http://html5boilerplate.com)
This is a really solid framework first and formost, [Paul Irish](http://paulirish.com) has done a fantastic job of pulling together a toolkit that really gives the developer and web designer a clean slate to work from. ​The project that I'm using it on needed to replicate an existing design but modernize the HTML and CSS to be more friendly and standards compliant. HTML5Boilerplate (H5BP) was perfect for this as it doesn't intrude on your design or setup. It really lets you decide how to build the site or application scaffolding.
The one thing I would say I like the best about H5BP is the main CSS file itself the thought, research and planning that went into the architecture of this stylesheet is impressive and even if you never use H5BP I highly recommend a perusal of this file.​ The way the file is laid out has seriously made me rethink some of my practices, especially always thinking mobile first, but that's for another post.
The bottom line on H5BP for me is if you need a base framework that's infinitely flexible and your project calls for a complex design that may not fit in with the grid frameworks that seem to pop up every 5 minutes this might be the one for you.​
##[Bootstrap](http://twitter.github.com/bootstrap)
Bootstrap is a completely different framework from the boilerplate in two ways. H5BP​ is about you building great sites with your own carefully crafted CSS, Bootstrap on the other hand is a carefully crafted style-guide that was build to empower developers to quickly and easily build an HTML framework around their Website and applications. Where Bootstrap excels and splits paths with most other frameworks is in how well all the different elements work together to build a complete toolkit that can be easily adapted into any application framework.
​Because Twitter built it to be pluggable you can use as much or as little of the framework as you want and for version 2 they've even built a generator to let you customize the build without knowing LESS, which helped me as I'm more of a SASS user. That being said where I think Bootstrap shines is when you dig in deep and where it makes sense use all the pieces together. 
I'm currently building an Administrative backend application and the what Bootstrap has allowed me to do it really focus on the functionality of the app rather than the ins and outs of making the styles work. With little exception my entire application has needed little extra CSS as Bootstrap has all the major areas covered. 
Scaffolding is there providing grids and layouts both witch are easily customizable, forms, tables, buttons alerts, and more are all included. They've really thought it through and every major item or event that you would use in the creation of an application is available.
Now It's not all roses for BootStrap at least for me as a SASS guy I'd rather see a framework at this level of detail and polish written in Compass but the usefulness of the built-in functionality and easy of use is more than enough to make me consider it for future projects.​
The verdict for Bootstrap, much like H5BP is that really depends on what the project needs. If your project needs a clean simple UI with a high degree of polish and you'd rather spend time perfecting your application logic than dealing with the inner workings of CSS this might be the toolkit for you.​
##Framework vs custom toolkit
While frameworks like Bootstrap are great at what they do; I feel that there is something about building your own toolkit that just feels right and really allows you to tailor it to the project your working on. This is one of the reasons why I've adopted H5BP as the foundation of my toolkit. However, I think as much as I strive for CSS perfection and only creating what I need we also need to be aware that sometimes that prebuilt framework can be just what the doctor ordered.