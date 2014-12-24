---
layout: post
title: "Rails with AngularJS: Frontend Setup"
date: "2014-12-17"
---
Earlier we have setup basic configuration as a starting point of our rails app. If you haven't read it yet, you can find it here ["Rails with AngularJS:Beginning"]({% post_url 2014-12-16-rails-with-angularjs-beginning %})

We are going to build our front-end first, In the form an AngularJS app. Normally I do build backend first in the pre-angular era. But, recently I notice a shift in my workflow. I will explain the reasons why this became my preference as this tutorial goes on.

##Setup Bower

And we are also going to manage our front-end assets with `Bower`. I find bower packages are more updated compare to their gems counterparts. Installing `Bower` need a little bit of `NodeJS`. On Mac, using `Homebrew` run this in the terminal.

`$> brew install node`

With `node` installed in your computer. Install `Bower` with the node package manager or `npm`.

`$> npm install bower`

We should not stop there, we need a gem to integrate bower with rails. Thus, we will add `gem bower-rails` to our `Gemfile`. And don't forget to 'bundle install'

We can now declare our assets. To do this we need to create a `Bowerfile` in the root of our project. `Bowerfile` acts pretty much the same as `Gemfile`, the main difference is that it'll fetch `bower-assets` rather than `ruby-gems`.

Your `Bowerfile` should look something like this:

{% highlight ruby linenos%}
asset 'angular'
asset 'bootstrap-sass-official'
{% endhighlight %}

As you may have guessed, we need to installed these assets too. Good thing that it has a `rake` command. To install bower assets run this command.

`rake bower:install`

You should be able find your bower-assets installed in `vendor/assets/bower_components`.

##Setup AngularJS

We are getting close on running our angularjs app on rails. Next step is to create a controller that will be our root path and where our view will be rendered as a angular app. Generate the controller with:

`rails g controller Home index`

This tells the rails generator to create a controller named **Home** and an action name **index**.

To make the **index** action as our `route-path`. Open and upate your `route.rb` and add the line `root "home#index"`. In yout `route.rb`:
{% highlight ruby %}
Rails.application.routes.draw do
  root 'home#index'
end
{% endhighlight %}

To link **angular** and jquery to your page, `application.js` will changed to:

{% highlight ruby %}
//= require jquery
//= require angular
//= require_tree .
{% endhighlight %}

And link **bootstrap** in your `application.css`:

{% highlight css %}
@import "bootstrap-sass-official/assets/stylesheets/bootstrap-sprockets";
@import "bootstrap-sass-official/assets/stylesheets/bootstrap";
{% endhighlight %}

##Simple AngularJS App

We need to know if we got our setup right. One way to do it, is to check the **Network Tab** on the firefox dev tools.

![dev tools - network tab](https://s3-us-west-2.amazonaws.com/blog-adooylabs/images/network_dev_tools.png)

Or we can create a simple app to check if `angular` and `bootstrap` is working properly. Open and edit your view in `views/home/index.html.haml`:

{% highlight haml linenos %}
.container-fluid{"ng-app" => "contactlist"}
  .panel.panel-success
    .panel-heading
      %h1{"ng-if" => "name"} Hello, {{ name }}
    .panel-body
      %form.form-inline
        .form-group
          %input.form-control{:autofocus => "", "ng-model" => "name", :placeholder => "Enter your name", :type => "text"}/
{% endhighlight %}

Open and edit `home.js.coffee` to initiliaze the angular app with this line of code:

{% highlight coffee %}
contactlist = angular.module('contactlist',[])
{% endhighlight %}

Let's see if you got our small angular app is working. When typing a text on the textfield input it should show a message like this:

![simple angular app](https://s3-us-west-2.amazonaws.com/blog-adooylabs/images/simple_angular_app.png)

Yay we nailed! Next stop will be creating our wireframe for our ContactList App.
