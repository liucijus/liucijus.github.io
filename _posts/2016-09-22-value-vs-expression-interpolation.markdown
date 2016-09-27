---
layout: post
title:  "Value vs. Expression interpolation"
date:   2016-09-27 11:00:00 +0300
categories: design
author: Vaidas Pilkauskas
---
Very useful feature of many programming languages is string interpolation. 
It is a great syntax for concise string formatting. Interpolated string is
nothing more than a template to be used to output formatted text. And it is a
primary responsibility of the interpolation feature. Scala supports two modes 
of interpolation: value and expression. 
  
{% highlight scala %}
val name = "Ozzy"
val surname = "Osbourne"
// value interpolation
val fullname = s"$name $surname"
  
// expression interpolation
val lengthMessage = s"Number of letters in the name ${name.length}"
{% endhighlight %}

And this is where I like Scala's syntax a lot - 
to eliminate parsing ambiguity, expressions need to be enclosed by braces, which
makes interpolated string look very ugly. 
And when something is ugly in the code, it makes me think what's wrong with 
it. Well, there's a problem - all expressions have their own responsibilities 
already. In the example above - expression is used to calculate name's
length, which is a separate responsibility on its own and placing length 
calculation into template is violation of *Single Responsibility Principle*.

While I don't want anyone to blindly follow this rule of not using expression 
interpolation in your code, in general I believe it's a good habit to prefer value 
interpolation over expression. It will make the code more readable without 
those distracting curly braces seeded in strings. And this gets to a clearer 
separation between responsibilities in the code.
If you let expressions creep into the code, they may end up as hard to find 
side effects (calling external APIs, invoking expensive refresh of a cache).

Scala allows to put values into blocks too, but why would you 
do that? Don't upset people who read your code.

