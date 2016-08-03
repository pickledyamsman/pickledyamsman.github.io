---
layout: post
title:  "How to Make Search and Filter Boxes for Angular"
date:   2016-07-04 15:40:15 -0400
categories: explanations
---

<p>For my final assessment one of the requirements was search functionality. I knew I needed to have a search box but I also wanted users to be able to filter based on multiple choices from a drop-down menu. Luckily with Angular these two functions are really easy to implement.</p>

<p>First off, let me show you the code I used to implement these features.</p>

    <span>
      <!-- search box -->
      <h3>Search: <input ng-model="restaurant.query" /></h3>

      <!-- filter dropdown with options -->
      <h3>Filter results by: </h3>
      <select ng-model="restaurant.orderProp">
        <option value="-votes">Most Votes</option>
        <option value="name">Alphabetically</option>
        <option value="-created_at">Newest</option>
        <option value="avg_price">Lowest Price</option>
        <option value="-avg_price">Highest Price</option>
      </select>
    </span><hr>

    <!-- ng-repeat to go over results -->
    <div ng-repeat="restaurant in event.restaurants | filter:restaurant.query | orderBy:'-votes' | orderBy:restaurant.orderProp">
      <div class="row">
    ...

<h3>Search Box</h3>
<p>Let's start out with the search box. Here we have a basic input that has an ng-model of restaurant.query. .query was used just to easily identify what it is being used for, you could use anything you wanted though.(search, find, etc.)</p>
<p>If you go down to the ng-repeat at the bottom you can see that restaurant.query is used again. It is used as a filter for the restaurants in event.restaurants.</p>
<p>Because of the data-binding abilities of Angular, what this will do is check all of the restaurants and return only the restaurants that match restaurant.query. This will work for any of the elements of a restaurant from just the name, the price, or any other part of a restaurant. </p>
<hr>

<h3>Filter By:</h3>
<p>The next box is a dropdown box that allows the user to filter by different options. This box is assigned an ng-model of restaurant.orderProp that will store the option value the user selects. You can have multiple options as I did just to give some variety for the user.<p>
<p>The options allow you to pick the variable from restaurants you would like to use to sort by. By putting a hyphen before the name you can reverse the order they would go in. "-created_at" gives you the newest results first, while "created_at" would give you the oldest first.</p>
<p>If you look down at the ng-repeat again you will see .orderProp in the last section. This is using orderBy which is built into Angular to order your results.
<hr>

<h3>Results:</h3>
<p>The last part of the code snippet is the ng-repeat that will actually filter the results. ng-repeat=restaurant in event.restaurants is showing what will be repeated. filter:restaurant.query will be the first filter that is tried. If a user typed anything in the search box that is what will be filtered. Next, orderBy:'-votes' will be used if there is no search. This will order the results by restaurants with the most votes. This acts as the default order. Last, whichever option was chosen in the sort by box will be used.</p>
<p>This gives the user multiple options on how to find the results they are looking for: search box, default of most votes, or choosing their own filter from a drop-down menu.</p>

<p>Hopefully this will help you implement your own search and filter functions in your own program!</p>
