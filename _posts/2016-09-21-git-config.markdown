---
layout: post
title:  "Use Different Git Config for Work and Personal Repos"
date:   2016-09-21 13:59:50 +0300
categories: tools
author: Vaidas Pilkauskas
---
The most frustrating thing with Git is that I make commits to repositories 
with wrong name and email. All the time! To solve this I have such entry in
global Git config:
```
user.name=Vaidas Pilkauskas
user.email=(none)
```
Which simply says that I need my name to stay the same across all
repositories, but I want my email to vary according organization. To solve
this, I've written a small script.
```
#!/bin/bash

ORIGIN=$(git config --get remote.origin.url)

if [[ $ORIGIN == *"wix"* ]]
then
  echo "Setting user info to Wix for the project"
  git config user.email vaidasp@wix.com
else
  echo "Setting user info to personal for the project"
  git config user.email vaidas.pilkauskas@gmail.com
fi  

```
This script tries to detect organization of the repo I work on (I am employed by [Wix.com](http://wix.com))
and picks email according to it. After I have freshly cloned repository,
first commit fails if I haven't run this script.
