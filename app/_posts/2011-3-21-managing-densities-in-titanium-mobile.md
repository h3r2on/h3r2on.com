---
date: 2011-03-21
layout: post
title: Managing densities in Titanium Mobile
slug: managing-densities-in-titanium-mobile
categories:
- mobile
- titanium
tags:
- Ti Mobile
- density
---

Building a cross-platfrom or Android application in Titanium Mobile means dealing with the various densities that exist; in total there are 6 levels you need to account for, Android low, medium, high and extra high. On iOS you have iPhone and iPhone 2x. As develpoers we have to deal with 5 of the six as medium in Android and standard iPhone resolutions and densities are the same.</p>
To aid developers with this issue I created a little function that comes in real handy. Note my example expects that you are using a namespace for your app.

    nameSpace.density = function(/*Object*/ map){
      var def = map.def||null; //default function or value
      if (typeof map[density] != 'undefined') {
        if (typeof map[density] == 'function') { return map[density](); }
        else { return map[density]; }
      }
      else {
        if (typeof def == 'function') { return def(); }
        else { return def; }
      }
    };

### Usage
To best use this function locate any situation that you need to set different values for the same object.

    //declared elsewhere
    nameSpace.osname = Ti.Platform.osname;
    // usage
    var a = (nameSpace.osname === 'android') ? nameSpace.density({xhigh: 45, high: 40, medium: 35 }) : 35;

this is just a simple example of how you could set different values to a variable but I think you can see the power that this can give especially when working with complex layouts.