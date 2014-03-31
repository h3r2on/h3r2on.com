---
date: 2012-01-24
layout: post
title: Your kidding me right... zip is a reserved form field name
slug: your-kidding-me-right-zip-is-a-reserved-form-field-name
categories:
- python
tags:
- plone
---

If only it where true, but it alas it's not. If you have the pleasure of using Plone as your CMS and you want to lets say make a form that captures a zip code, you can't name that form field 'zip' as its a reserved word in plone. 
Some other common words are also reserved. Lets say you need to have a form submit to oh I don't know paypal, you've got major issues. 
Hidden fields for a paypal form require login, discription and type. Guess what, yup all reserved words. So how does one get around this. 
A little python and javascript that's how. Nicely the Plone Form Gen devs added overrides so you can modify the form on submit and on load like so:

    return \
    """
    jq(document).ready(function(){
      jq("#archetypes-fieldname-login-1 input").attr("name","login");
      jq("#archetypes-fieldname-type-1 input").attr("name","type");
      jq("#archetypes-fieldname-description-1 input").attr("name","description")
    });
    """


nothing to special but it's a stupid hack that shouldn't be needed IMO.