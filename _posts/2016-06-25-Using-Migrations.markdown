---
layout: post
title:  "Using Migrations"
date:   2016-06-25 21:04:15 -0400
categories: explanations
---

<p>Something that I had a lot of trouble with when I was starting with Rails was using migrations. For the longest time I was so worried about using migrations, because I thought I would break my entire program if I did one thing wrong. I learned later that there were easy fixes for all of these things and now I run migrations with no fear at all. Hopefully this guide will help others overcome their migration fears.</p>

<p>The basics of migrations are creating a new migration.</p>

    rails generation migration CreateUsers name:string password:string

    This will generate the following migration:

    class CreateUsers < ActiveRecord::Migration
      def change
        create_table :users do |t|
          t.string :name
          t.string :password
        end
      end
    end

<p>This is something that you should already know but I am going over it just for a baseline.</p>
<p>Lets say you realized you needed another column for your table. You can do another migration for that.</p>

    rails generate migration AddUsernameToUsers username:string

    This will generate the following migration:

    class AddUsernameToUsers < ActiveRecord::Migration
      def change
        add_column :users, :username, :string
      end
    end

<p>On second thought you don't need that username column. You can easily remove it with another migration.</p>

    rails generate migration AddUsernameToUsers username:string

    This will generate the following migration:
    
    class RemoveUsernameFromUsers < ActiveRecord::Migration
      def change
        remove_column :users, :username, :string
      end
    end

<p>These last two migrations only really need to be done if you have already run your migrations with rake db:migrate. If you haven't done that yet you are able to just edit the migration file and then run your migration.</p>

<p>Another option you have is to just start over. Use rake db:rollback to go back one migration and make changes or rake db:drop to drop all of your tables and start from stratch. This won't delete your migration files but instead lets you edit them and migrate again and get back to where you need to be.</p>

<p>If you need to reset your database there is a command for that too. rake db:reset will drop all of your tables, run all the migrations and seed your data back into the database.</p>

<p>With these migrations and commands you can run migrations and never have to worry about "breaking" your database. You are free to make as many mistakes as you need until you get that program working right.</p>

<p>There are more migrations than this. This is just a basic intro into migrations. If you want to look more into it you can see the active record migration documentation here: <a href="http://edgeguides.rubyonrails.org/active_record_migrations.html">Migrations</a></p>