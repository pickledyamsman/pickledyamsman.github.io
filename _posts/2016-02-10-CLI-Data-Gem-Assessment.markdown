---
layout: post
title:  "CLI Data Gem Assessment"
date:   2016-02-10 13:07:15 -0400
categories: learn assessments
---
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The project that I had to do for this unit was to create a Ruby gem. I had a few ideas but decided that it would be fun to have a program that would return the top album of the year someone was born.

You can see the program here: <a href="https://github.com/pickledyamsman/birth_year_album">Birth Year Album</a>

<br>
<h3>Planning:</h3><hr>

The basic setup for the program I wanted was:

    user types birth_year_album

    "What year were you born?"

    1985

    "1985 - Born in the U.S.A. - Bruce Springsteen - United States"

    "Would you like to see any other years?"

<br>
<h3>How it works:</h3><hr>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The information comes from <a href="https://en.wikipedia.org/wiki/List_of_best-selling_albums_by_year_in_the_United_States">List of Best Selling Albums by Year in the United States</a> This was the simplest site to use to scrape the data from. Wikipedia gets this information from the Billboard charts since 1956 when they first started collecting their data. Billboard's site has the information broken up by year and then within the pages for the years the charts are broken up into individual weeks. The problem with Billboard's site is the information is not compiled for the top selling album of the year, only for the week. So this was not a reliable source of information compared to Wikipedia.



&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;After the program takes in the data from the user it first checks to see if they inputted a number and then checks to see if it is in the allowable range (1956-2015) that has data. If it is too high, too low, or not an allowable input it will give a custom response for each scenario and prompt the user to provide new input.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;When the user provides appropriate input, the program iterates through the wikipedia page and finds the year that was input. The artist is the next cell after the year. The album name is three cells after the year. The program instantiates a new album with this information and returns it to the user as:

    The top album of album year was:
        
    ------------------------------------

    album name by album artist

    ------------------------------------


The program quits when the user inputs 'exit'.

<br>
<h3>Problems:</h3><hr>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The major problem I had with this project was dealing with the table data. The last <td> of the page is a nil value which was giving my an error with my .text call. I fixed this by iterating over all of the <td> tags aside from the last one.

<br>
<h3>Example:</h3><hr>
Here is a video demo of the program in action:

<iframe width="854" height="480" src="https://www.youtube.com/embed/BmSu4B9424k" frameborder="0" allowfullscreen></iframe>
