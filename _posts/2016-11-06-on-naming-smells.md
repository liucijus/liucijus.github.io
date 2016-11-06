---
layout: post
title:  "On Naming Smells"
date:   2016-11-06 16:00:00 +0200
categories: design
author: Vaidas Pilkauskas
---
This post is a comment on a few things from an amazing blog post 
by Peter Hilton on [Naming Smells](http://hilton.org.uk/blog/naming-smells).
It describes multiple types of naming problems and suggests how to fix them.

### Short and Symbolic Names
My favorite post parts are about short and symbolic names. I think they 
explain why so many of us run away from math theory after seeing the first 
formula. The same feeling I have about most of the things in academia - 
things look cryptic. What makes me sad about it is seeing the same cryptic 
naming patterns cripple functional programming communities. And I think it 
is a number one reason why we are so bad in adopting functional languages. 
It is not the category theory that scares people away, but how we communicate 
it in our code.

### Prefixes May Have Meaning in Boolean Properties Naming
One place I do not fully agree with the author is dropping prefixes like `is` from 
the names. In general, what I really like about dropping prefixes is that it 
makes us think more about the meanings of our names. Dropping prefix from `isVictory` 
renames variable into `victory`, which on its own has a broader meaning. 
It can be an object with much more functionality than very limiting boolean 
type. If I ask "is victory", I'm used to get "yes" and "no" answers. 
If I ask just "victory", I am not sure what it can answer. "yes", "no" or maybe 
"in progress"? In type-safe languages we have types to communicate this meaning,
but I see types more as tests which compiler runs, and not a tool to improve 
readability. Type information in a lot of cases is one or more steps away from 
the reader (even with an IDE provided shortcut). There can be good uses of prefixes 
to emphasise intent of the variable. For example, prefixes like `has`, `can` or `was`
bring their own bit of information into the name. If dropped, this meaning is 
lost. I would say don't follow this rule blindly. If you cannot come up with 
a good name, stay with a prefixed one. If you can give a good  name without 
prefix - go for it. Good names must be explicit.

### Give Specific Names to Variables
I like to be very specific in collection variables naming. Blog post contains 
a part on multiple words naming where `appointment_list` is renamed to `calendar`. 
In my understanding a calendar can mean more than a list of appointments. 
For example, it may hold properties like name, owner and maybe some other information
like reminders. I usually name lists as plural forms of items they contain. 
In this case it would be `appointments`. Another example is where 
`company_person` is renamed to `employee`. I think this one is very good 
naming example. Why is it good? It is shorter, contains more information. 
For variables specific names are better, while generic names are worse. 
It may not be the case for types naming, where reusability drives to have more generic names.

It is very easy to find counterarguments for every good naming practice 
if it is done outside the context where name has its meaning. 
Removing code smells without understanding why something is bad, may do more harm than good.
