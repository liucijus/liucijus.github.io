---
layout: post
title:  "How to Install Global npm Packages in Your Home Dir"
date:   2017-01-08 13:59:50 +0300
categories: tools
author: Vaidas Pilkauskas
---
If you do not use [nvm](https://github.com/creationix/nvm), it may be annoying that each time
 you install global npm package, it asks for super user right. It is fairly easy to solve 
 this problem by adding small configuration to your `.npmrc` file:
 
{% highlight bash %}
prefix=~/.npm-packages
{% endhighlight %}
Now all your global packages will be placed in `.npm-packages` folder. You need to create this
 folder manually.

And then add your local npm bin folder to your PATH. I have such line in my `.bashrc`:
{% highlight bash %}
export PATH="$PATH:$HOME/.npm-packages/bin"
{% endhighlight %}

I hope this helps someone.
