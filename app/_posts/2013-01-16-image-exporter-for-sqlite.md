---
date: 2013-01-16
layout: post
title: Image exporter for sqlite
slug: image-exporter-for-sqlite
comments: true
categories:
- tooling
tags:
- python
- sqlite
- utility
---

As a mobile app developer I often need to extract images out of a sqlite database to do manipulations on. One of my clients made a nifty python script to extract images out of their database. 
It was single purpose built and lacked the ability to quickly call and customize the input and output it so I've tweaked it a bit and added the ability to use parameters from the command line. Hopefully someone finds it as useful as I do. You can find it on [github](https://github.com/h3r2on/imgOut).