---
layout: post
title:  "Why Would I Use a Switch"
date:   2016-09-07 10:09:15 -0400
categories: explanation
---

<p>Working as a learn expert has led me to some students with questions that really got me thinking. I know the answers to most questions but some of them I think I know the answer but later in the day I keep thinking about it and how I could better answer their question. This is one of those examples.</p>

<p>The other night I had a student with some questions about switch statements in JavaScript. At first, he just needed help with the syntax of his switch statement, because honestly, switch statements are kind of weird looking when you compare them to loops. They have a completely different syntax than for, while, and if loops so it naturally leads to students being confused.</p>

<p>Let's tackle the first part. The basic syntax of a switch:</p>

    switch (expression){
      case value1: 
        statement;
        break;
      case value2: 
        statement;
        break;
      default : 
        statement;
    }

<p>So most people reading this already know what a switch statement looks like so the above code seems obvious. What the student was having problem with was what to put into the value field for the cases. They were passing something along the lines of expression === 5. When we deal with comparing a value in other loops we would use a statement like that so it seems like a reasonable mistake to make. The teaching moment was explaining that because we had already passed in the expression to switch it already knew that we were comparing it to the differnet cases and the student understood what they needed to do and fixed their code. Simple stuff!</p>

<p>A few minutes later the same student came back with the question that made me start thinking and eventually write this blog post.</p>

    "If a switch statement is just an if...else statement, why would we use switch?"

<p>This is an awesome question! The simple answer is that I don't really use switch statements. I prefer the look of if else statements to switch statements and that is honestly the only reason I prefer them. Other developers prefer the look of a switch statement so they use that instead and I get why they do.</p>

<p>Switch statements are more readable. They show you exactly what they are evaluating and what they return all in a simple list from case a to case z. I can't think of a simpler was to show this myself. It makes sense for readability why you would want to use them.</p>

<p>The other, bigger, reason I have seen for using switch statements, is that they are processed faster. There seems to be some debate on if they are always faster in deeply nested switches, but there doesn't seem to be any debate about simple switches vs. simple if...else statements. Some tests I read show switches performing twice as fast as if...else statements. Now, this isn't going to show in the relatively simple projects we work on in learn but in a giant program it would be a noticeable difference.</p>

<p>I think that these are the basics to why someone would use a switch over an if...else statement. I think for the simple programs I make I will probably keep using if...else statements, but maybe now I will experiment with mixing in some switch statements for extra practice.</p>