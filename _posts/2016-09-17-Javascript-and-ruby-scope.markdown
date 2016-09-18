---
layout: post
title:  "Javascript and Ruby Scope"
date:   2016-09-17 10:09:15 -0400
categories: explanation
---
<p>Scope is something that I am very familiar with in Ruby, but lately I have been doing more JavaScript coding and scope doesn't work the same way in the two languages. This is also something that a lot of Learn students struggle with at first. I figured I would write up some differences between the two both for my own sake and for other students. This is going to be mainly about variable scope just to start out more with the basics. This sets the groundwork to start working with other aspects of scope as well.</p>

<h3>Variable Scope</h3>
<hr />
<p>Variable scope is where a varibale can be accessed in a program. The two types of scope you have are global and local scope. Global scope means that a variable can be used anywhere in the program. Local scope only lets variables be used in certain parts of the program. Local scope is the scope that has more issues because global scope just affects everything.</p>

<h3>Ruby Scope</h3>
<hr />
In Ruby, to use a variable inside of a method you have to pass in the variable unless it is defined globally.

~~~ruby
name = 'Matt'
def say_my_name()
  return name
end

puts say_my_name()
~~~

This won't word because name wasn't passed into the method. To fix this we could pass name in like `say_my_name(name)` or we could declare the name variable inside of `say_my_name().` The latter doesn't make much sense because then the method could only be used for the one name. Passing in variables is definitely the preffered way to deal with this. This makes it easy to protect varibales in Ruby because they just won't work unless they are used the right way.

<h3>JavaScript Scope</h3>
<hr />
In JavaScript, you can use variables that are outside of the function unlike in Ruby. Here is a function that does the same thing as the Ruby method above but this one will work.

~~~javascript
var name = 'Matt';
function sayMyName() {
  return name;
}

console.log(sayMyName());
~~~

This code works in JavaScript thanks to hoisting and declared functions get access to variables outside of themselves. When a variable is defined in the top level of JavaScript it is automatically a flobal variable. The way that JavaScript uses variables like this is less secure for how variables are dealt with. This is why people use closures to stop variables from being used globally.

<h3>Conclusion</h3>
<hr />
<p>This is just a really basic explanation of scope between JavaScript and Ruby, but it is something that took me a bit to initially understand when I moved from Ruby to JavaScript. I imagine it would be much more confusing if you were used to how JavaScript dealt with scope and then moved over to Ruby.</p>
