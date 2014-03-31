---
date: 2013-05-17
layout: post
slug: rename-css-on-compile
title: Rename CSS on Compile
comments: true
categories:
- web
tags:
- SASS
- compass
---

I've always wondered if there was automated way to add the .min to production CSS files on compile when using Compass. It just so happens this tiny bit of ruby will do the trick for you.

{% highlight ruby %}  
require "fileutils"
    
on_stylesheet_saved do |file|
  if File.exists?(file)
    filename = File.basename(file, File.extname(file))
    File.rename(file, css_dir + "/" + filename + ".min" + File.extname(file))
  end
end
{% endhighlight %}

By hooking the `on_stylesheet_saved` compass callback we can gain access to the filename and then we can use that to do our work. For a list of other callbacks and options from compass see the [configuration reference]("http://compass-style.org/help/tutorials/configuration-reference/").
