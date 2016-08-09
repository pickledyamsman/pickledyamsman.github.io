---
layout: post
title:  "Adding Friend Connections to Program"
date:   2016-08-03 13:24:15 -0400
categories: explanations
---
<p>Something I have wanted to learn how to do for a while now was adding the ability to add and remove friends in my programs. Using a User model I can easily create multiple users with logins, but adding the functionality for connections between these users was something I just couldn't figure out on my own. I did some research and here's an easy way I found to implement this!</p>
<hr><br>

<h3>Generator</h3>
<p>The first thing you need to do is generate a friendship controller and model.</p>

    generate scaffold friendship user_id:integer friend_id:integer create destroy
    rake db:migrate

<p>This will create the friendship.rb model and the friendships_controller.rb controller with create and destroy.</p>
<hr><br>

<h3>Models</h3>
<p>Then, we need to set up to relationships that both of these models will have.</p>

<strong>models/user.rb

    has_many :friendships
    has_many :friends, through: :friendships
    has_many :inverse_friendships, class_name: "Friendship", foreign_key: "friend_id"
    has_many :inverse_friends, through: :inverse_friendships, source: :user

<strong>models/friendship.rb

    belongs_to :user
    belongs_to :friend, class_name: "User"

<p>This set up allows up to link the users to other users using their user_id. The inverse relationships allow your friends to have your id but it doesn't automatically have you added as their friend. This can be used for a profile page to show who has linked to you so you can link back to them at a later time.</p>
<hr><br>

<h3>Controllers</h3>
<p>The next step is setting up the friendships controller. This set up will let users add and remove friendships.</p>

<strong>controllers/friendships_controller.rb

    def create
      @friendship = current_user.friendships.build(friend_id: params[:friend_id])
      if @friendship.save
        flash[:notice] = "Added friend."
        redirect_to root_url
      else
        flash[:error] = "Unable to add friend."
        redirect_to root_url
      end
    end

    def destroy
      @friendship = current_user.friendships.find(params[:id])
      @friendship.destroy
      flash[:notice] = "Removed friendship."
      redirect_to current_user
    end

<p>This is pretty self explanatory. The controller has basic create and destroy for friendships.</p>
<hr><br>

<h3>Views</h3>
<p>The last part of implementing this is adding it to the views. You will need an add friend button to let users add friends.</p>

    <%= link_to "Add Friend", friendships_path(friend_id: user), method: :post %>

<p>Put this next to a user name so the current user can add them as a friend.</p>

<p>Then in your user's profile they should be able to see both the friends they have added and which people have added them as friends.</p>

<strong>users/show.html.erb

    <h2>Friends</h2>
    <ul>
      <% for friendship in @user.friendships %>
        <li>
          <%= friendship.friend.username %>
          (<%= link_to "remove", friendship, :method => :delete %>)
        </li>
      <% end %>
    </ul>

    <p><%= link_to "Find Friends", users_path %></p>

    <h2>Friended by Users</h2>
    <ul>
      <% for user in @user.inverse_friends %>
        <li><%= user.username %></li>
      <% end %>
    </ul>

<hr><br>

<p>The code examples here are from <a href="http://railscasts.com/episodes/163-self-referential-association?autoplay=true">Railscast</a>. The information is from reading a lot of stackoverflow and the railscast that I just linked.</p>
