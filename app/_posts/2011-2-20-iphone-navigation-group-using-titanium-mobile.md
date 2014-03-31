---
date: 2011-02-20
layout: post
title: iPhone Navigation Group using Titanium Mobile
slug: ihone-navigation-group-using-titanium-mobile
categories:
- mobile
- titanium
tags:
- titanium
- ios
- navGroup
---
I've been using Appcelerator's Titanium Mobile for the past month to build cross platform app for work and I thought I'd share this bit as I had a hard time finding what I needed. 

I'm of the camp that the UI for my app should be a native to the platform as possible, Ti Mobile does a good job at this for the most part. But when it came to navigation concepts the documentation for the iPhone nav group was lacking. Luckily [Arraon Saunder's blog](http://blog.clearlyinnovative.com/post/1624173028/titanium-appcelerator-quickie-navigation-groups) has a great quick walkthrough. The one thing missing from his article is that if your developing for Android too you'll need some modification. Here's my modified code.


if (Ti.Platform.osname === 'iphone') {
	var navGroup = Titanium.UI.iPhone.createNavigationGroup({
		window: win1
	});
	win1.navGroup = navGroup;
	win.add(navGroup);
}

this will now make a navgroup only if the device says it is iOS. If you neglect this android will through some nasty errors at you. Now that we've separated this we must also separate out the open window call like so.


	if (Ti.Platform.osname === 'iphone') {
		navGroup.open(win2,{animated:true,fullscreen:true});
	} else {
		win2.open({fullscreen:true});
	}

Now there you have it a Iphone nav bar that will also work in android. Of course a better solution might be to create your own navigation scheme so that it's identical on both platforms but this makes it fully native.