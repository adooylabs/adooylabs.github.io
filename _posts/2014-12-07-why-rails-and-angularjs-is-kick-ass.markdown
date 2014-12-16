---
layout: post
title: "Why Rails and AngularJS is Kick-Ass"
date: 2014-12-07 20:46:00
categories: angularjs, rails
---

I'm currently working on an app that I planned to be in multi-platform. Users should be able to use the app with a browser or a native mobile app. I knew it then that I will be creating a `RESTFUL API`. A ruby on rails backend that will render `JSON` responses.

But, I wasn't too sure about how I would implement the front-end for the web application. I just couldn't decide which javascript framework to use. I have tried `backbonejs` and `emberjs` before, but I wasn't really happy about it. It took me a while to finally decide to dive into **angularjs**. I was a little hesitant at first. Scared of the terms and jargons like "Directives". Scared that probably I would be wasting my time.

But, after hours of putting my mind into it and started learning. I had a change of heart. What made me change my mind?  Well, aside from its ever growing community, contributors, and plugin. Here's a few of its features that I think unique to **angularjs**:

+ **Two Way Data-Binding** - this mean that angular automatically synchronize all data between your model and view components. This also means no more elaborate callback code to update your view.

+ **Directives** - this is basically a marker on your html code that tells angular what is it function or relation. You can even write your own directive or submit it as a plugin.

+ **Dependency Injection** - a good way of keeping track of dependencies, and make testing easier.

Overall, it is a great client-side framework. Great for creating "single-page applications" or SPA.  There is a little bit of learning curve but once you get a good grasp on directives, the scope, and how code is organized with modules and injections you should be pretty comfortable after that.

Having a ruby on rails backend and angular for the client-side would be a pretty kick-ass setup. You can even deploy either on the same heroku server or ran on a separate server.
