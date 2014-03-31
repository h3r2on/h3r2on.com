---
date: 2012-08-17
layout: post
title: 'Twitter API changes: the impact'
slug: twitter-api-changes-the-impact
categories:
- opinion
- web
tags:
- twitter
- api
---

The new​ API changes Twitter will be introducing in version 1.1 are going to hurt a large segment of Twitter users and I wonder if Twitter realizes the impact. My site is an example on my Let's be Social page I have a block that displays my Twitter timeline I'm not sure that will stay around with the new changes and I know I'm not alone. Last night David Walsh of [davidwalsh.name](http://davidwalsh.name) cited that the changes are going make him drop a Twitter block for his upcoming redesign. I can only imagine that most others will as well.
###What's the big deal?
To put it plainly, authentication. Previous to 1.1 you could get the public timeline of any Twitter account without authentication​ this made it easy for Website owners and hosting providers like Squarespace (my host) to give you custom Twitter widgets to place on your site, without using the garish widget that Twitter provides. This has all changed. With the new API version authentication is required for all API calls that means that there is no longer an easy way to provide this Website integration for tweets. The authorization method that twitter uses OAuth requires user interaction to accept the authentication and get a token that can be used to interact with the API. This added step stops the current behind the scenes methods that are used to get the data you see on Websites now.
###There must be an alternative!
There is an alternative its name, xAuth. xAuth allows an application or website to authenticate and make API calls without user interaction. Great then why are you moaning about this? The issue is that Twitter holds all the xAuth keys you have to specially request access to use xAuth and Twitter decides if you are worthy or not. While I'm sure bigger developers will be able to obtain xAuth access the big question is will Twitter allow anyone with a website that wants a custom Twitter block xAuth access, I have a hard time believing that is the case. The answer we'll be fed will surely be use the first party widgets, for some this will be an ok solution, but for those that want that custom look or just want a cleaner UI this is not going to be good enough and Twitter is leaving them out in the cold.
I understand that many a spammer used this method to target users and send spam, but there should be another option for those that just want to put a customized twitter timeline on their site or in their mobile app​ without resorting to forced authentication.