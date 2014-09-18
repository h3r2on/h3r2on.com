---
published: true
date: 2014-09-18
layout: post
title: 'transitioning bewteen xcode versions'
slug: transitioning-bewteen-xcode-versions
comments: true
categories:
  - mobile
  - titanium
tags:
  - xcode
---

Every year around this time is painful for iOS developers as Apple unleashes a new xcode. Dealing with the changes is made difficult by the fact that the version overwites the old, but with a little work we can setup or mac to deal with these yearly changes in style.

What we'll need

* terminal
* previous Xcode installed (5.1.1 as of this writing)
* New Xcode installer pulled from the apple dev site (6.0 as of this writing)


Ok so let get prep our environment in Finder or at the terminal let create two new directories.

    mkdir /Applications/Xcode5.1
    mkdir /Applications/XcodeBeta

So what we've done is create spaces for us to hold the current Xcode version outside of the root Applications directory, this is the "magic" that will help us work with multiple versions. The second folder will give us a clean place to put future Xcode beta versions as Apple releases them.

Now in Finder move the current Xcode.app into your Xcode5.1 directory so you should have some thing like in the image below.

[Finder](/assets/xcode-move.png)


You are now ready to install the new version of xcode. This will install into `/Applications/Xcode.app`.

Ok so now when you build apps from the commandline or Titanium studio it will use the new Xcode version, but what if we want to build from the old version?

luckily apple gives us tools for this. Time to pull out the trusty terminal the `xcode-select` command gives us a number of options heres a few of them:

    xcode-select --print-path
    xcode-select -version
    xcode-select -switch xcode_folder_path

The first option will give us the path of the current xcode in use. The second option will obviously give us the current version of xcode. The final option allows us to switch which xcode is active. So if we wanted to switch to our 5.1.1 version is would look like this:

    xcode-select -switch /Applications/Xcode5.1/Xcode.app

This will now allow us to build of the old SDKs to switch back simply run:

    xcode-select -switch /Applications/Xcode.app

For Titanium devs using the command line to build your apps there is actually an easier way to switch back and forth.

first make sure you have the latest Ti CLI node package installed (3.4.0-beta in our case)

    sudo npm install -g titanium@3.4.0-beta

Now when you go to run you build you just need to reference the ios SDK you want to target with the `-I` option so to target iOS 7.1

    ti build -p ios -device-id "iPhone Retina (4 inch)" -I 7.1

That build string will build our project and open the iphone 5(S) simulator running iOS 7.1, for more options see `ti build -h` for the full command line build options.

There you have it the long and short of working with multiple Xcode versions, by creating new folders for old releases and using the `xcode-select` command you can stay productive and ensure your apps will be ready for whatever Apple throws at us next.
