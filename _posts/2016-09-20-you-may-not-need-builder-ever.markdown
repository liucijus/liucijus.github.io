---
layout: post
title:  "You May Not Need Builders Ever"
date:   2016-09-20 13:59:50 +0300
categories: design
author: Vaidas Pilkauskas
foo: FooBar
---
One of the greatest advatages of using 
[Builder pattern](http://www.javaworld.com/article/2074938/core-java/too-many-parameters-in-java-methods-part-3-builder-pattern.html) is giving names 
to methods in languages without named parameters support. Here's builder example in Java.

{% highlight java %}
Foo foo = new FooBuilder()
  .withId("abc")
  .withName("Some meaningful name")
  .build();
{% endhighlight %}

Constructor can be used to build the same object, but parameter 
meanings are disguised. In this case design also suffers from the 
same types (well, all of them are `String`s), which makes it easy 
to accidentally put arguments in wrong order.

{% highlight java %}
Foo foo = new Foo("abc", "Some meaningful name");
{% endhighlight %}

Some languages (eg. Scala) let us specify parameters by name. 
Using named parameters is a great way to obsolete usage of verbose 
Builder pattern and retain the same level of readability.

{% highlight scala %}
Foo foo = Foo(id = "abc", name = "Some meaningful name")
{% endhighlight %}

But what if only some of the parameters need to be specified 
while others can stay as is? Scala supports default parameter values.

{% highlight scala %}
class Foo(id: String, name: String = "Some meaningful name")

Foo foo = new Foo(id = "abc")
{% endhighlight %}

So if you work with modern language, consider ditching verbose 
Builder pattern in favour of your language features. 

Scala has a `copy` method on case classes which can be used as replacement 
for Builder, but I find its name to be very low level and communicating 
wrong message to the reader most of the time.

{% highlight scala %}
// BAD: I need a foo with specific name, but what I do is 
//      communicate copying
val foo = foo.copy(name = "New Name")

// GOOD: method name communicates intention - reader does not know 
//       how object is constructed
val foo = aFooWith(name = "New Name")
{% endhighlight %}
