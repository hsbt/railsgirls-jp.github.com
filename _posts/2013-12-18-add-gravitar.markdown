---
layout: default
title: Adding Graviatar to you app
permalink: gravatar.html
---

# Adding Gravatar to your App

*Created by Catherine Jones*

This guide assumes that you have already built a Rails Girls app by following this [app development guide](http://guides.railsgirls.com/app/) and added authentication using [Devise](http://guides.railsgirls.com/devise/).

### Important

You need to have an e-mail address registered with Gravatar for this to work. If you do not already have one you can go to [gravatar.com](http://en.gravatar.com/).

## *1.*Add the Gravtastic gem

Open up your gemfile and under your `devise` gem add

{% highlight erb %}
gem 'gravtastic'
{% endhighlight %}

In the terminal run

{% highlight sh %}
bundle install
{% endhighlight %}

This will install the gravtastic gem. Then remember to restart your rails server.

## *2.*Set up Gravatar in your app

Run the following command in your terminal:

{% highlight sh %}
rails g gravtastic:install
{% endhighlight %}

## *3.* Configure Gravatar

Open `app/views/layouts/application.html.erb` and in the

{% highlight erb %}
<% if user_signed_in? %>
{% endhighlight %}

section but before the

{% highlight erb %}
<% else %>
{% endhighlight %}

add

{% highlight erb %}
<%= image_tag current_user.gravatar_url %>
{% endhighlight %}

Now open you app in your browser and login with an e-mail address that is associated with a Gravatar. You should be able to see your Gravatar.
