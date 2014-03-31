---
date: 2011-04-19
layout: post
title: Code Igniter and GET vars
slug: code-igniter-and-get-vars
categories:
- web
tags:
- php
- codeigniter
- get-vars
---

I've begun using CodeIgniter to build a API service at work and an early stumbling block was the seemingly conflicting messges it gives about access to `$_GET` variables.
The input class clearly says, "Destroys the global GET array. Since CodeIgniter does not utilize GET strings, there is no reason to allow it." Well that's not very helpful when recieving callback urls from a number of services that require get to work. Unfortunately this is miss leading as down farther they give you this method.

    $this->input->get();</p>

What they should have said in their documentation is that they have closed off the standard way to access the `$_GET` input array and have instead made a more secure and CI way to access the array.
Example from within any controller that you expect GET vars you can simply request it like so:

    $something = $this->input->get("something", TRUE) // True adds XSS filtering

Hopefully this will help mitigate some confusion for someone.