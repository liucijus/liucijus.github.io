---
layout: page
title: Talks
permalink: /talks/
---
#### Understanding Git
Do you want to be effective in how you use Git? So this talk is what every Git
user needs to know and understand about the tool. We will briefly look into 
how git tracks changes internally, how its architecture allows to add number 
of history related workflows which are based on merging, rebasing, history 
rewrite and what implications do they bring.

#### Can You Trust Your Tests (An Introduction to Mutation Testing)
Nobody argues these days that unit tests are useful and provide valuable 
feedback about your code. But who watches the watchmen? Or, in other words, 
who is testing tests themselves? Let's talk about test code quality, code 
coverage and introduce mutation based testing techniques. Ideas behind 
mutation testing are nothing new in academic world, but only now become 
recognized by software developers while programming their production 
systems. This talk will look into how mutation testing can be used to 
improve your test-driven development cycle and will try to answer if 
existing tooling is mature enough to be used while coding your daily tasks.

#### Understanding Mocks
Mocking plays important role in unit testing, and is a great way to isolate
your dependencies that your system under test depends on. Many of us do not 
question libraries we use, what problems they solve. And some of us have strong 
opinion on what mocking is, and what it is not. Let’s retrospect on current 
state of popular mocking frameworks like Mockito and JMock. How are they 
different from each other and where their weaknesses are. The second part of 
the talk is an analysis of what it takes to write a mocking framework from 
scratch in Java 8. This talk is aimed at a curious developer who wants to 
understand how mocking tools work and hopefully it will hint on things where 
such tools can be improved. Source code for the example mocking library can be 
found here: https://github.com/liucijus/jinsist

#### TDD: Discover Implementation by Stepping Small
Enough with the theory! Let's look into how classical TDD techniques are 
applied to discover algorithm implementations by moving forward with baby 
steps and triangulating into more generic implementation. This talk is fully 
based on live coding in Scala, but does not require any prior experience with 
the language. It covers the following techniques: baby steps, transformation 
priority premise, mutable vs. immutable code, functional programming habits 
that may get in the way. It will end with introduction to tail call 
optimization by leaving audience with an open question which code was more readable.
_I've given versions of this talk in Scala, JavaScript, Ruby & Python_

#### Developer Tests - Things to Know
There are many great talks that discuss challenges developers 
face when writing software tests. In this talk let's look 
at test design problems that may seem to be simple but yet 
fundamentally important and often misunderstood even by 
experienced programmers.

#### Java 8 Time API
Overview of Java 8 Time API. Trying to answer why time are API are complex and hard to get right.

# Workshops

#### Web Security: Authentication
**Level: Beginner/Advanced**.
Workshop covers cookie hashing, secure password storage and many more.

_I can run it in JavaScript, Java_
