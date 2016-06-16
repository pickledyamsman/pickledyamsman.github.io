---
layout: post
title:  "My Angular Mistakes"
date:   2016-06-16 17:06:15 -0400
categories: explanations
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Right now it is assessment eve and I am putting those extra finishing touches on my program before the big day. This is my final assessment and I have been working on it for a little over a week now between unpacking and getting my house settled.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The last two days have been about mistakes with my program. I am not trying to say that my program is perfect, just that I realized some mistakes before it was too late. Hopefully, this post will help you avoid the same mistakes I made.

<br>
<h4>1. Wrong Structure</h4>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;I was reading a bunch of walkthroughs and guides preparing for this program. I knew there was a knowledge gap between what I had learned and what I hoped to accomplish with the program. The only way to fix it? Read about it. The program with reading so much on these topics was I saw twenty+ ways to format my angular program. I longed for the standardized ways of previous languages. Not everything is standardized in Angular I quickly learned. 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;My program has a directory structure different than what we learned in the lessons. I don't feel like this is a big problem. Instead of breaking things up closer to the MVC structure we used in previous languages, my program is broken up based on functionality. All navigation is together(view, controller, and services) all in one folder called nav. I saw a good amount of code grouped this way and honestly I liked it and went for it. This only caused minor headaches when trying to reference past programs I wrote using the other format.

<br>
<h4>2. Wrong Formatting</h4>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;What really messed me up was one early guide to get Devise working correctly. They did not use the Angular structure where the module and service were defined at the bottom of the file. They defined everything at the top with an extra function call. I am not sure where this came from but I started using it just to match my starting files from the Devise guide. I decided to switch everything back to the way that was taught in the course. Everything works the same but I think there must be a reason for the way we were taught.

<br>
<h4>3. Old Advice</h4>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A bit into my program I realized something was wrong. I had googled around for an answer to a problem. What I found on stackoverflow worked and everything was looking good until I ran into a page about how that method was deprecated. It had been deprecated over a year ago. I hadn't checked the date on the post or answer and ended up with a solution that really didn't work. This caused me to have to work twice as much to fix the problem the old advice created.

<br><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;I guess the main point I am trying to make with the post is to be carefull where you get help from. I used old advice and guides using different formats than I was comfortable using. Both of these things caused extra work for me in the long run.