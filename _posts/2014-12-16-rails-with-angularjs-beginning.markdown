---
layout: post
title: "Rails with AngularJS: Beginning"
date: "2014-12-16"
---

Earlier this month I posted ["Why Rails and AngularJS Kick-Ass"] ({% post_url 2014-12-07-why-rails-and-angularjs-is-kick-ass %}), And  I owe you guys a demo. I'm planning to write a series of tutorials  on how to make `Ruby on Rails` and   `AngularJS` play nice together. We will be building a simple "contactlist" app from the ground up.

##Prerequisites

This tutorial assumes that you have previous experience in writing simple CRUD app in rails. And have some knowledge in writing coffeescripts. We will be using *HAML* markup instead of *HTML*. Having Rspec, Jasmine, and Capybara skills is a plus. It also assumes that you already have your development environment setup and ready to go.

##What We Need

  * Ruby 2.x
  * Rails 4.x
  * Coffeescript

##Setup

Let's start by creating the structure of the app in rails. by running the command.

`rails new contactlist --skip-test-unit`

skipping the *unit-test*, because we will be using  `rspec and capybara` later on.

### Gems

Now that we have a rails app structure, we now need to add all the gems we will be using in our app.  Your starting `Gemfile` should look something like this:

{% highlight ruby linenos%}
source 'https://rubygems.org'
# Bundle edge Rails instead: gem 'rails', github: 'rails/rails'
gem 'rails', '4.1.6'
# Use SCSS for stylesheets
gem 'sass-rails', '~> 4.0.3'
# Use Uglifier as compressor for JavaScript assets
gem 'uglifier', '>= 1.3.0'
# Use CoffeeScript for .js.coffee assets and views
gem 'coffee-rails', '~> 4.0.0'
# Build JSON APIs with ease. Read more: https://github.com/rails/jbuilder
gem 'jbuilder', '~> 2.0'
# Use unicorn as the app server
gem 'unicorn'
# you can use any database you prefer
gem 'pg'
# using haml markup instead html
gem 'haml-rails'
{% endhighlight %}

Now that we have a basic gems in the `Gemfile`, let's install them with:

`bundle install`

Don't also forget to configure your `database.yml`

{% highlight yaml %}
development:
  adapter: postgresql
  host: localhost
  port: 5432
  database: contactlist_development
  schema_search_path: public
  encoding: utf8
  template: template0
  pool: 25

# Warning: The database defined as "test" will be erased and
# re-generated from your development database when you run "rake".
# Do not set this db to the same as development or production.
test: &test
  adapter: postgresql
  host: localhost
  port: 5432
  database: contactlist_test
  schema_search_path: public
  encoding: utf8
  allow_concurrency: true
  template: template0
  min_messages: error

cucumber:
  <<: *test
{% endhighlight %}

Once this is configured, our next step is to build the `API` backend. We will be creating our *models* and *controllers*.

next: [Rails with AngularJS: Frontend]({% post_url 2014-12-17-rails-with-angularjsfrontend %})
