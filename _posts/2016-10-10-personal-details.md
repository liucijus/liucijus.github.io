---
layout: post
title:  "Personal Details in Tests is Unnecessary Distraction"
date:   2016-10-27 17:00:00 +0300
categories: design
author: Vaidas Pilkauskas
---
One of the first things you have to do in unit test is to decide which values to pass to your 
system under test. Task seems to be very straightforward, but not that easy after all.
Have you ever seen funny data values? Like this one:

{% highlight scala %}
val name = "Mickey"
val surname = "Mouse"

sut.register(name, surname) mustBe successful

{% endhighlight %}

Or maybe not so funny, but being your colleague's name? 

{% highlight scala %}

val name = "Vaidas"
val surname = "Pilkauskas"

sut.register(name, surname) mustBe successful

{% endhighlight %}

While good sense of humor is great strength in social life, it easily 
distracts us from the problem we are solving. In tests it is just additional 
load for our brains. <br />
But the second example isn't related to humour. "What's wrong with it?" you may ask. 
A problem here is social impact of a personalization. <br />
Imagine situation where this code was written by senior developer and he has used 
his name and surname in the test data. <br />
A person who just joined the company needs to 
make changes to this test as part of her new task. If she wants to change it, she 
may think, if it is allowed to change the name, does it have any meaning, is there
a practice to name data after yourself. Would it be offensive if she deletes 
unneeded tests with senior developer's name and then adds a new one with her name? 
This looks like small issue - it is easy to ask that person right? But what if he 
is on month long vacation? Or maybe there's another reason why it is hard to reach
him. Situations like this add additional load for our brains. <br/>
**Personal details prevent us from cleaning after ourselves**. And they must be avoided.
In addition irrelevant details disguise the real meaning of test data and thus fail to 
communicate test's intent. For example, it is not clear if we are working with 
a person that has to be our employee or not. <br />
Test data values should communicate their meaning well. I use boring names like
_CustomerName_, _CustomerSurname_. You may develop different naming convention, 
it does not really matter as long as it helps communication. If I need a list of 
multiple names, I suffix values with numbers - _TestCustomer01_. It helps 
tracing failed tests so that you can quickly spot if your naming maps to the correct 
order of elements in the resulting list.

