---
layout: post
title:  "Starting with SASS"
date:   2016-08-10 12:53:15 -0400
categories: explanations
---
<h3>Why use Sass?</h3>
<p>Sass is supported by Rails by default and it is much more powerful than basic CSS. The code is easier to read and you can do some amazing stuff with it that CSS just can't handle. Furthermore, lots of job postings looking for Rails developers also want you to be familiar with Sass, so it's a no-brainer that you would want to learn at least the basics of Sass.</p>
<hr><br>

<h3>Getting Started</h3>
<p>There really isn't any prep work needed to get things working with Rails. If you look in your gemfile there is already a gem for Sass included.</p>

    gem 'sass-rails', '~> 5.0'

<p>It should look something like that. Next, if you want to create a sass file you just go to your stylesheets folder in assets/stylesheets and create a file like (test.css.scss). The .scss extension means sassy css and it is the extension that is most commonly used for Sass now.</p>
<p>Since the file is already in the right place to be picked up by the asset pipeline it will automatically put all of your CSS rules together when you run the program so you don't need to do anything else.</p>
<hr><br>

<h3>What can you do with Sass?</h3>
<h4>Variables</h4>
<p>Variables in CSS are something I didn't even know I wanted, but once I started using them there is no turning back. If I want to set my background color as a variable I just do it like:</p>

    $bg-color: #9fc;

<p>I can then call that color just by providing the variable name.</p>

    .background {
      background-color: $bg-color;
    }

<p>After Sass is processed it will turn the variable into CSS and work fine.</p>

<h4>Nesting</h4>
<p>In Rails we are used to everything being nested and easily read because of this nesting. Basic CSS doesn't have this but Sass does and it makes everything look so much better.</p>

    nav {
      a {
        display: block;
        padding: 4px;
        text-decoration: none;
      }

      img {
        display: block;
        padding: 6px;
      }
    }

<p>This works exactly as you might expect it to and when Sass is processed it will split everything up to work properly in CSS.</p>

<h4>Mixins</h4>
<p>Mixins are used to groups CSS declarations, most notably for vendor prefixes, that you will use multiple times in your application.</p>

    @mixin column-count($value) {
      -webkit-column-count: $value;
      -moz-column-count: $value;
      column-count: $value;
    }

    .header { @include column-count(3); }

<p>This mixin can be used on multiple items and you just pass in the value you would like for each of them. This saves you from having to write the vendor prefixes over and over.</p>

<h4>Extending</h4>
<p>Another thing in Sass that works like Rails is extend. You can use a selector and extend its declarations to other selectors easily.</p>

    .p1 {
      margin: 2em;
      padding: 1em;
      color: #c69;
    }

    p2 {
      @extend .p1;
      background-color: blue;
    }

<hr><br>
<p>Most of the things Sass does look similar or exactly the same as things you can do in Rails. This is great because it is an easy transition if you are already comfortable with Rails and it makes your CSS much easier to work with!</p>
