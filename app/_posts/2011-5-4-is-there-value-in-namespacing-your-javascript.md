---
date: 2011-05-04
layout: post
title: Is there value in namespacing your javascript?
slug: is-there-value-in-namespacing-your-javascript
categories:
- web
tags:
- namespacing
- js
- javascript
---

Lately I've found myself architecting my larger JS projects into name spaces to not only avoid collisions but to make my life as a developer easier. 
Quick example I'm restructuring my universities Google maps code, its a big grouping of functions and persistant variables. In my mind it has been easier to have `uwo.map.someFunction` then a list of 40 or so random functions polluting the global scope, but i'm starting to wonder if this approach slows my code down. 
The more I read the more I get conflicting thoughts about my process, there doesn't seem to be a best practice regarding namespacing or whether it's a good practice. 
My methodology has followed what I've seen at Google and Yahoo; a nested object hierarchy that in many ways goes to the java way of thinking about class packaging. Not necessarily a good thing to do in JavaScript, but how does one organize a large js project in a meaningful way, to the developer, yet keep it fast an efficient as is grows. On that topic i'm stuck.