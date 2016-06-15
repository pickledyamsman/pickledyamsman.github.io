---
layout: post
title:  "Directives"
date:   2016-06-15 13:07:15 -0400
categories: explanations
---

<h3>Why should you use directives?</h3><hr>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Directives are what make Angular so powerful. They help make pages more responsive and let us manipulate the DOM either through built in directives or custom directives that we define. Most of the tools we use in Angular are directives, so if you are using Angular you don’t have much use for the language if you aren’t using them.
  

<br>
<h3>Built in directives</h3><hr>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;If you have messed around with Angular at all, you have seen some of the built in directives. Certain directives: ng-app, ng-click, ng-class, ng-repeat, ng-submit, ng-controller, etc. are standard and a lot of programs will use them.<br> 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;There are more than that and here is a handy list to show them with descriptions <a href="http://www.techstrikers.com/AngularJS/angularjs-built-in-directives.php">Built in Directives</a>. This is the easy part of directives so get that down!

<br>
<h3>Custom directives</h3><hr>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;We create custom directives so that they are reusable throughout the program and in other programs we might make in the future.


A Really Basic Example:

{% highlight angular %}

app.directive(‘sayhi’, function() {   
  scope: {},
  restrict: “E”,
  template: “Hello, {{ user.firstName }} {{ user.lastName }}”,
  replace: ‘true’
});

{% endhighlight %}

<strong>Let’s break this down:</strong>

<i>scope: {}</i>: makes it so that sayhi has its own scope. This is useful for reusing this directive in other programs since it is not dependent on its parents scope.

<i>restrict: “E”</i>: makes this only active on elements with sayhi like <sayhi></sayhi>. This directive will be activated whenever there is a <sayhi> element.

<i>template: "Hello, "</i>: When the directive is activated it will use the user’s first and last name to welcome them using .template = “Hello, {{user.firstName}} {{user.lastName}}”; This will be displayed in the <sayhi> element on the page.

<i>replace: ‘true’</i>: takes the <sayhi></sayhi> element and replaces it with Hello, firstName lastName. This is done because there will only be one user at a time. You would not have it set to true if this was an element that would be changed in the future.<br><br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Directives are really important. This is just a small sampling of them but there is much more to learn. I hope this helped you understand the basics.
