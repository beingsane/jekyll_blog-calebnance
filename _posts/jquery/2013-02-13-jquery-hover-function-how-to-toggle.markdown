---
layout: post

title: "jQuery Hover Function How To Toggle"

date: 2013-02-13 13:56:21 -0500

excerpt: Easy way to have the jQuery hover function fire on mouse-in / hover over

comments: true

categories: jquery
tags: howto javascript jquery
---
This is a really easy way to have the **jQuery hover** function fire on mouse-in (hover over) and return to normal on mouse-out (no longer hovered over element). Here is the jQuery function:

{% highlight JavaScript %}
<script>
  $('.yourclass').hover(function(){
    alert('hover in');
  }, function(){
    alert('hover out');
  });
</script>
{% endhighlight %}
