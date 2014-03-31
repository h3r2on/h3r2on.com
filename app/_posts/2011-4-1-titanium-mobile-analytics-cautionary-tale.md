---
date: 2011-04-01
layout: post
title: Titanium Mobile Analytics...a cautionary tale
slug: titanium-mobile-analytics-cautionary-tale
categories:
- mobile
- titanium
tags:
- analytics
- Ti Mobile
---
So this week I launched my first Titanium developed application for both Android and iOS. So naturally I want to see what people are using in the app.
To this end, in the development stage I set a number of different analytics events that tell me what feature they're using. Being a good developer I followed the documentation as to how to implement my analytics events in the documentation, at that time and as of this writing [they show](http://developer.appcelerator.com/apidoc/mobile/latest/Titanium.Analytics-module) an example like this:

    Titanium.Analytics.featureEvent('app.feature.blah',{product:'killer'});

Now if you saw this you'd then assume that if you create a similar setup say `app.feature.directory` that when your app hits the store and people start using this feature that the analytics Appcelerator displays would show how many times `app.feature.directory` was called, I certainly did. Well we'd be wrong, in their analytics tool they only show `app.feature`. Ok that's fine I bet I can at least get an export of my analytics data right, it is my data after all? Again you'd be wrong.
Wait you'd say I'm a pro developer I'm paying you for support and access to 6 months of analytics I need my analytics. Their answer, tough luck, we'll let you know if and when we decide whether we'll allow you to export your data. Then to slight us who followed their example a bit more; they created a brand new FAQ on (3/30/2011) letting you know that you won't be getting that third level analytic data. Thanks Appcelerator, love you too.
So let this be a warning to you, don't trust Titanium documentation. I know I don't anymore.
## Update
Progress! I'm happy to report that Ti Analytics is now finally showing navFeatures and FeatureEvents data in the stats dashboard views. How ever their are still issues.
Any data you passed to the featureEvent is still unseen. As I said before this would be fine if we could ge the raw data but we still have no access to dump our data to do the calulations ourselves. Again I'm disappointed by the lack of feature completeness that we paying devs are pay for.
For my purposes I'm looking into google analytics for tracking purposes, the depth of data and tracking abilities offer more than appcelerator has shown they can offer.