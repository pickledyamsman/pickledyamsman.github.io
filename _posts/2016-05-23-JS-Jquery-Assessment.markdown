---
layout: post
title:  "JavaScript/jQuery Assessment"
date:   2016-05-23 13:07:15 -0400
categories: learn assessments
---
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The jQuery assessment had me  refactoring my previous Rails program to better use JavaScript and jQuery. You can see the program here: <a href="https://github.com/pickledyamsman/club_posts/tree/rails_javascript_assessment">School Clubs</a><br>


<h3>Planning:</h3><hr>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;What I wanted to do with the program is have certain forms show without a page reload. Namely: club creation, club edit, post edit, and post creation forms. These forms have a button that the user presses and the form pops up on the screen, does the specified action, and shows the results on the page.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;In addition to this, deleting both clubs and forms is done with a javascript event that fades out the item and removes it from the database without a page refresh.

<br>
<h3>How it works:</h3><hr>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;To expand the program I focused on the different types of clubs because this was a section that was not given much attention in my original program. With this program users have a separate types management page that is accessible from the homepage.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;In the types management page users have a button that allows them to show all of the types that are currently available and how many clubs have that club type. These are shown as a link that links to the type show page for that item. There is also a type creation field so users can create custom club types which was not available in the original program.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;In creating posts to a club I noticed that there was no way of dealing with posts that were too long. In the learn curriculum there was a section that focused on exactly this and I implemented it into my program with a button that expands a post over 17 characters.

<br>
<h3>Problems:</h3><hr>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The hardest part of this assessment was converting some of my functions into a separate file to be used through the whole program like the previously mentioned more button. The original code in the labs used it on the page as an inline function and I didn't want to repeat the code on multiple pages.

<br>
<h3>Example:</h3><hr>
Here is a video of the program in action!

<iframe width="854" height="480" src="https://www.youtube.com/embed/pNccm9FHDo4" frameborder="0" allowfullscreen></iframe>