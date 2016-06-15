---
layout: post
title:  "Rails Assessment"
date:   2016-04-26 13:07:15 -0400
categories: learn assessments
---
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;I created a program called School Clubs. School Clubs is a simple message board for clubs. You can see the program here: <a href="https://github.com/pickledyamsman/club_posts">School Clubs</a><br>


<h3>Planning:</h3><hr>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;I knew that I wanted to do something along the lines of a message board but couldn't figure out what I wanted. My wife is starting grad school in the Fall, and that gave me inspiration for this program.

<br>
<h3>How it works:</h3><hr>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The login is handled with both Devise and Oauth using Google to authenticate the login. Once a user is logged in they are able to create, edit, or delete a club. Within that club the user can post messages to the club. These messages show the user that created them with their email address. A user can edit or delete a comment for the club.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Clubs and users have dependencies that make it so if the club or user is deleted their posts are also deleted from the database.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A user can also edit or delete their account through Devise. They are able to log out and log in as well.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The nav bar changes based on whether a user is logged in or not. Home is always provided. If a user is logged out they will see sign up, log in, and log in with Google. If they are logged in they will see options to edit their account or log out.

<br>
<h3>Problems:</h3><hr>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The biggest problem I had with this assignment was getting Google Oauth working. Google seemed like the likely 3rd party login because most students would be using Google. Using Google required Ruby to be in version 2.3.0 or higher but that wasn't immediately shown so just the upgrading took a long time.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Creating the authentication seemed like it would be easy but consistently gave me problems.

<br>
<h3>Example:</h3><hr>
Here is a video of the program in action!

<iframe width="854" height="480" src="https://www.youtube.com/embed/AVqKGJW6cX8" frameborder="0" allowfullscreen></iframe>