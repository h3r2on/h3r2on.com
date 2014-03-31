---
date: 2013-02-01
layout: post
slug: full-sql-statements-with-ti-alloy-collections
title: Full SQL statements with Ti Alloy collections
comments: true
categories:
- mobile
- titanium
tags:
- alloy
- sqlite
- backbonejs
---

Prior to version Alloy 0.3.5 the sql adapter only supported `SELECT * FROM table_name` which left much to be desired. However, which the release of 0.3.5 you can now query to your heart desire.

{% highlight javascript %}
  var Library = Alloy.createCollection('book');
  library.fetch({
      query: 'SELECT * FROM table_1 INNER JOIN table_2 ON table_1.id=table_2.id'
  });
{% endhighlight %}

The key here is a key change to the sql adapter. To get this functionality in your Collections you'll need to change your models' adpater type from 'sql' to 'sql_new'. This hits the new adapter and allows for the query option. Once Alloy 1.0 releases the adapter will return to just 'sql' but retain the new functionality.