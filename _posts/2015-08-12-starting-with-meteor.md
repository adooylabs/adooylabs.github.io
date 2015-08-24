---
layout: post
title: "Starting with Meteor"
date: "2015-08-18"
---

There is a new framework in town and it's built on top of NodeJS. A friend recently introduces me to this new framework, 
cause he knew that I've been attempting to dive into NodeJS lately and Insisted that I should checkout Meteor. So I did, and it turn out 
to be an interesting find. Meteor has a lot of potential and the future looks promising.

The future is real-time, the futre is one code fits all. And Meteor has these features and I came to appreciate and like. 

## Installation

On you linux or unix machines install the latest official Meteor release from your terminal:

`curl https://install.meteor.com/ | sh`

On windows, [Download the official Meteor installer here.](https://install.meteor.com/windows)

Once you've install Meteor, create a new project: 

`meteor create testapp`

Change directory to the project's root folder.

`cd testapp`

Then type `meteor` to run it locally and should see this in you terminal:

{% highlight bash %}
=> Started proxy.
=> Started MongoDB.
=> Started your app.

=> App running at: http://localhost:3000/
{% endhighlight %}

Visit 'http://localhost:3000/' on your favorite browser and there you go, your very first meteor app.
    
