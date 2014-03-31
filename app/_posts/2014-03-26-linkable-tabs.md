---
published: false
date: 2014-03-26
layout: post
title: 'Creating linkable tabs with Bootstrap'
slug: creating-linkable-tabs-with-bootstrap
comments: true
categories:
  - web
tags:
  - javascript
  - bootstrap
---

In building a new site a work using Bootstrap 3 we came across a section that necessitated the use of tabs but also needed each tab to be directly linkable.

Linkable of course is easy in fact Boostrap out of the box is linkable. However the key requirement was if someone clicked on a tab that the url in the browser bar should change to make linking possible for anyone.

At first I thought this could be a bit more challenging. But alas a quick look over at the bootstrap docs and MDN and I found an intersting solution.

The code:

{% hightlight javascript %}
var hash = document.location.hash;
var prefix = "tab_";

if(hash){
  $.(".nav-tabs a[href=" + hash.replace(prefix, "") + "]").tab("show");
}

$.(".nav-tabs a").on("shown.bs.tab", function(e){
  window.location.hash = e.target.hash.replace("#","#" + prefix);
});

{% endhighlight %}

Let's tackle the first part, by grabbing `document.location.hash` we're going to get what is currently present if anything in the hash part of the URL. Given (http://h3r2on.com#tab_mytab) hash would equal "tab_mytab". Setting the prefix is also a good key this lets us break the one to one unity between the tabs ID and won't cause the page to incorrectly scroll if we don't want that behavior.

the if statement detects if we have a hash and if after striping our prefix off it matches the url of one of the tabs it instructs Bootstap to make if visable. so far pretty straight forward stuff.

The second part of that script is where the url magic is. by adding a eventListener on the "shown.bs.tab" event we can now know when a tab has been displayed and on display we instruct the browser to replace whatever the current location.hash was with the appropriate prefixed hash for the target tab.

Demo Link


Have cleaner or better solution hit me up in the comments.
