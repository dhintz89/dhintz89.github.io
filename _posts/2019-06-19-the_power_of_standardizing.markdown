---
layout: post
title:      "The Power of Standardizing"
date:       2019-06-19 22:04:50 +0000
permalink:  the_power_of_standardizing
---


One thing that has really been impressed upon me time after time as I've been learning code is the power of standardizing.  As a Process Improvement Architect, standardizing is my bread and butter - take a process that is poorly defined and build out some standard rules and it allows for all kinds of efficiency gains.  But in coding, this is taken to another, incredibly impressive, level.  Nowhere has this been more apparent to me than in using Sinatra to build my first web app called "[My Town Tracker](https://github.com/dhintz89/my-town-tracker)."  Let me explain:

### Readability
This is the most obvious benefit, but it cannot be overstated.  When you use standardized coding "best practices" your code becomes easily followable, this applies to yourself, but more importantly it applies to other people.  This is critical if you are working with another person, or asking someone more experienced for help.  The ability for someone new to jump in and support you without spending hours getting acquainted with what you've already done can be a lifesaver.

### Language-hopping
Learning Ruby was hard, it felt like drinking through a fire hose for the majority of the time and the deeper I dove in, the more complicated it became.  Coming out of that on the other end though - I felt like I really conquered the language.  Looking forward at the curriculum, I can see that next up is to learn a totally new language - Javascript - but as I look through the curriculum and start knocking out the early lessons, I realize that it's all feeling extremely familiar.  Yes there are a few differences I'll need to get my head around, but because of standardization in certain concepts, keywords, datatypes, and even some of the specific notations, it feels less like I'm learning a new language and more like I'm learning how to talk like a "Southerner" instead.  I'm hopeful that this standardization will allow me to learn multiple languages over time and become a very flexible developer.

### Extending the language
All that is well and good, but it's to be expected, nothing groundbreaking.  But this next part is where the magic comes in.  Coding is complex.  It takes a TON of instruction to get even the simplest of applications running.  When I think back to my first project - the Ruby CLI Gem - and imagine creating my Sinatra project with that level of explicity, I immediately start getting anxiety just thinking about it.  But because the developer world was able to come together and agree on a standard set of coding patterns, these patterns could be turned into more formalized libraries and out-of-the-box methods which can actually take care of an astonishing amount of the work for you without even needing to lift a finger.  

The most powerful example I've seen so far is ActiveRecord.  By using ActiveRecord to link my Ruby Classes (Models) to my database Tables, not only does my code get greatly simplified, and I'm talking life-changing simplification, but I get to basically cut out learning an entire new coding language (SQL)!  

Take this snippet of code from my Sinatra Project:
```
class User < ActiveRecord::Base
  has_many :places
  validates :name,  presence: true
end
class Place < ActiveRecord::Base
  belongs_to :user
end
```
Doesn't look like much, and to be honest, it's not.  But if I had to write that functionality out explicitly, it would look more like this:
```
class User

  @@users = []

  def initialize(username, password, name)
	  @username = username;
		@password = password;
		@name = name;
		@places = [];
	end
	
	def username=(username)
	  @username = username;
	end
	
	def username
	  @username;
	end
	
	def password=(password)
	  @password = password;
	end
	
	def password
	  @password;
	end
	
	def name=(name)
	  @name = name;
	end
	
	def name
	  @name;
	end
	
	def add_places(place_list)
	  place_list.each do |place|
		  @places << place;
		end
		@places;
	end
	
	def places
	  @places;
	end
end

class Place
  
	@@places
	
	def initialize(name, user)
	  @name = name;
		@user = user;
	end
	
		def name=(name)
	  @name = name;
	end
	
	def name
	  @name;
	end
	
	def user=(user)
	  @user = user;
	end
	
	def user
	  @user;
	end
end
```
And the kicker?  That's only half of what ActiveRecord is doing - it doesn't even include all of the interaction with the SQL database that's also happening in the background!  And on top of that, consider that this is just a tiny portion of the relationships that are built into my project... All I can say is thank goodness for ActiveRecord!

But how is this possible?  When you look through the long version you can see a ton of repeated patterns.  Additionally, the entire
```
class Name
    def initialize(instance)
	 @instance = instance;
	end
	
	def add_object(object)
	  @objects << object
	end
end
```
pattern will be repeated for anything with a has_many relationship, and likewise for the full class pattern for each of the other relationship types.  ActiveRecord simply takes ALL that repeated *standardized* language and rolls it up into the keyword `has_many` so when you see that "has_many", it's essentially the same as writing the full block of longer code above.  I don't know about you, but I find that to be truly amazing.

The only catch with this miracle of standardization is that everything has to be written *exactly* according to the standards.  One letter that gets capitalized where it shouldn't and it all comes crumbling down.
