---
layout: post
title:  "Angular Assessment"
date:   2016-06-16 11:48:15 -0400
categories: learn assessments
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The Angular assessment had me creating an Angular frontend with a rails backend: <a href="https://github.com/pickledyamsman/whats-for-dinner">Whats for Dinner?</a><br>


<h3>Planning:</h3><hr>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;For this program I wanted to solve a common problem my wife and I have. We can never decide where we are going to eat. This program was going to help solve that problem.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;I wanted to use a simple up/down vote system where we enter in some restaurants and vote on which place to go. The winning restaurant would be the place we eat at.

<br>
<h3>How it works:</h3><hr>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The program uses Angular-Devise to authenticate the user and lets them sign up, sign in, and log out. Depending on if they are logged in or not shows different links in the nav bar. Home is always available. Users can view anything even while not logged in but they are not able to create anything unless they are logged in.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A user can create new events for different meals they plan on having. Inside of an event users can create restaurants that are tied to that event and store votes for them.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Restaurants can be searched and filtered. The filter accepts multiple inputs that affect the way the restaurants are sorted. The search functionality works on any part of the restaurant so whatever the user inputs is searched, including name, location, etc.

<br>
<h3>Problems:</h3><hr>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This entire program was a real pain to be honest. Integrating Angular and Rails proved to be much more work than I had anticipated. Setting up authentication through Devise had me reading multiple guides and walkthroughs but eventually it worked.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;I found that the way I wrote the program is very different than the way we were taught but I think it holds up even with the differences. It still does what is intended.

<br>
<h3>Future:</h3><hr>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;I wanted to initially have groups that a user could join that would have common restaurants and let users see the other members but I ultimately felt that this functionality was beyong the scope of the program. But it could be added in the future.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The way it works now is a user can vote multiple times on a page refresh. In the future I would like to make it so a user can only ever vote up and down once but I couldn't find a reasonable way to do that. This will need some further research.

<br>
<h3>Example:</h3><hr>
Here is a video of the program in action!

<iframe width="854" height="480" src="https://www.youtube.com/embed/c_0RwpBJHm0" frameborder="0" allowfullscreen></iframe>