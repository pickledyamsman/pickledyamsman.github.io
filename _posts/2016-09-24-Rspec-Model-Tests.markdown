---
layout: post
title:  "RSpec Model Tests"
date:   2016-09-24 11:04:15 -0400
categories: explanation
---

<p>Testing is something that I kind of glossed over while I was going through Learn. I just used the generated tests and didn't add any of my own because I thought that would be good enough, but I am in talks with a company and they told me they want me to write RSpec tests as my starting out point. This has gotten me into learning and writing tests. Since it was something I didn't focus on in the course I figured it was also something that a lot of students also wouldn't focus on. A lot of the information I have learned has been through <i>Everyday Rails Testing with RSpec</i> which has proved to be a valuable resource! This will be the first in a set of blog posts going over different aspects of things I have learned using RSpec.</p>
<br />

<h2>What a Model Spec Should Have:</h2>
<hr />
<p>
  <ul>
  <li>A create method that should be valid when valid attributes are passed to it.</li>
  <li>Tests to make sure that when invalid data is passed to it, it falis validation.</li>
  <li>Tests to make sure class and instance methods perform as expected.</li>  
  </ul>

  These are the basic tests that every model spec should have as a baseline.
</p>

<h2>Bacic Model Spec Syntax</h2>
    require 'rails_helper'

    describe Contact do
      it "is valid with a firstname and lastname" do
        contact = Contact.new(
          firstname: 'Matthew',
          lastname: 'Cianciolo')
        expect(contact).to be_valid
      end
    end

<p>This is your basic test for the model. We are creating a new contact and assigning it values. Then we check if the new contact is valid. Since RSpec is pretty close to natural language it is easy to read the test.</p>

Some things to note: `require 'rails_helper'` is needed at the top of the program to run the tests. Also, what is in it...do is up to you. You should try to make it short but also describe what you are testing. Tests should only expect one thing so a short description should be easy to write. When we write an it...do statement it should start with a verb like it, gets, shows or something like that.

<h2>Invalid data tests</h2>
<hr />

<p>The other big thing we need to test in model specs is if the model will be created when we pass in invalid data. This is simple enough to do by making our contact have one of the values be nil and checking that it wasn't created.</p>

    it "is invalid without a firstname" do
      contact = Contact.new(firstname: nil)
      contact.valid?
      expect(contact.errors[:firstname]).to include("can't be blank")
    end

<p>Here we set the variable we are testing to nil and then we check the errors to see if the right error is passed.</p>

<h3>Conclusion</h3>
<hr />
<p>Model Specs are fairly straightforward to set up and work with. They are mostly checking that the validation you set up is working correctly and that the model is created correctly.</p>

<p>Next week: Controller Specs!</p>