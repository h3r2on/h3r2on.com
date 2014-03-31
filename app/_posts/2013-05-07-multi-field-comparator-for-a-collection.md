---
date: 2013-05-07
layout: post
title: Multi-field comparator for a collection
slug: multi-field-comparator-for-a-collection 
comments: true
categories:
- mobile
tags:
- alloy
- backbonejs
- collections
---

There are many times when being able to sort a collection against two or more distinct columns is needed. Unfortunately Backbone doesn't provide a default way to do that via the comparator function. However, making it happen inside our collection definition is quite straight forward. 

For my example I'll be sorting a list of cities and states. The end result we want is to have a list of cities sorted by state. 

With the default comparator we get one or the other sorted cities or states.

{% highlight javascript %}
comparator: function(Model){
  return Model.get('city');
  // or
  // return Model.get('state');
}
{% endhighlight %}

To get at multiple we need to understand what the comparator function is actually doing. Backbone uses the `sortBy()` function to prepare the collection in a always ordered stack(it's not really a stack but go with me on it). Running a compare on a collection returns a -1, 0, or 1 based on where the model should be placed compared to the models it's compared to, thus keeping the collection in a ordered state by moving the order based on the result.

In order to sort on multiple columns we need to give backbone a result that can be sorted that utilizes both columns/fields values. The best way I've found is to use a normalized string. In our city and state example our data is all alphabetical so sorting against them will be easy. If your data set is numerical, however be careful that all your numerals are the same length, i.e. 002, 100, 045. other wise you will get mismatches in the compare.

Now our comparator looks like this:

{% highlight javascript %}
  comparator: function(Model){
    var location = Model.get('state') + '-' + Model.get('city');
    return location;
  } 
{% endhighlight %}

Which will return strings like 'WI-Madison', 'WI-Milwaukee'. By putting the `Model.get('state')` first I'm able to sort on state before dealing with individual cities, thus getting me my end result.

Using the same approach you can now sort on as many columns or attributes as needed and get the results you want. The key is remembering how the comparator works by ensuring you return a string that can be uniquely sorted. With this rule in mind you can finally do some advanced sorting on your collections.