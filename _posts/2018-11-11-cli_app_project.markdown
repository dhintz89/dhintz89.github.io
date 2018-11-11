---
layout: post
title:      "CLI App Project"
date:       2018-11-11 19:51:18 +0000
permalink:  cli_app_project
---


The first Student Project in the Flatiron Curriculum is to create a CLI Application from scratch.  This was the first time I would be working 100% without instructions to guide me and up-front, it seemed like a pretty tall order.  I decided that, like all other big projects, the first thing I needed to do was to get organized.

### First thing's first, what needs to happen before I could get started?

Firstly, I needed to come up with an idea.  One of the reasons I'm so excited to learn how to code is to create applications that would make my life easier, so I thought like a programmer.  What is something that I find myself doing repeatedly that I would benefit from being able to simply 'push a button'?  A few ideas popped into my head, but one really stood out.  I often spend a lot of time trying to think of what to do in my spare time (often more time than I actually spend doing the thing...).  This is not something that can be solved with a simple scraping program, but it's certainly a start.  
Idea: found.

Next, I needed a high-level idea of what it would actually do.  I decided that I wanted to get a list of current events that were going on around me, broken out by various categories.  To keep things simple, I wanted to see events with a start and end date since these are the events I'd prioritize.  So at a high level, I wanted to see a bullet list of what's going on, and then I can choose one to get the details...easy enough to plan out, now time to start designing the program.

### How to get started?

At the beginning, I really only had a general idea of how the program would work.  I got the project set up easily enough by following Avi's instructions in [this video](https://learn.co/tracks/full-stack-web-development-v6/object-oriented-ruby/final-projects/cli-data-gem-walkthrough).  Then it was time to start coding.  I wasn't sure what objects I would be using right off the bat, but I knew I'd need a scraper.  So, I started off by creating a single file: Scraper.rb.  I wrote a description into that file, with each action on a separate line.  This looked something like this:
```
# Ask User for location and activity input
# Search an events website using these parameters
# Scrape a list of event options from the website
# Create an object instance for each one
# Display the results and ask User to choose one
# Go to the event specific webpage
# Scrape the remaining details
# Add details to existing instance
# Display the full set of details
```
This would serve as the skeleton outline of my entire program.  Underneath each action, I began to write a code to perform the action stated.  At first, most of these programs operated independently of each other (i.e. "Create an Object Instance" simply created an object instance, it did not take info from scraper).

### Organizing the App

Once I had some code in place, the app started to take form.  I could see that I would only have one type of Event Object since I would create a summarized version and then fill out details once selected, rather than create separate objects for summary and full events.  I could also see at this point that the app would entirely be made up of the interaction between the Scraper and the Event.  This led to a completed file structure: CLI, Scraper, and Event would be located in the lib folder, with the Executable File in the bin.  

It was easy enough at first to separate the different actions into each folder, I just needed to think about what each object should actually do.  Scraper should handle getting data - search website and scrape data for the Event Class to use.  Event should self-create instances to hold the data the Scraper passes in.  And the CLI should handle collecting user input and displaying results.  Once I was done with that I started to build out the various interactions, such as using user input (CLI) to search the website (Scraper) and then populate the summary event based on the returned data (Event), and I quickly learned that it wouldn't be quite so simple.

In order to make the code easier to read and to work with, I ended up shifting some of the responsibilities around, for example, it ended up making much more sense for the Event Class to handle displaying itself, rather than trying to pass that function over to the CLI.  After working out all of the interaction, I ended up with this structure:
* CLI would handle the program's flow, display menus, and get the user's menu selections
* Scraper would ultimately handle collecting the User's search parameters, find and search the websites, display activity categories, and Scrape and return data sets to populate the Event attributes.
* Event would store, self-create, and self-enhance event instances as well as displaying both the summary event list and the full event details

Quite a bit of shifting code around between the files, but in the end it looked and ran much cleaner than trying to force it into the original model.

### Finishing Touches

Once all of that was complete, there was still quite a bit of work to do.  While the program *technically* worked at this point, there was a lot to still be desired.  Namely, making the user interface come to life and not look like the user is entering information into "The Matrix."  This part was fun because it was all about researching to creatively come up with new ways of improving the code and the interface.  I learned a lot about formatting, things like HEREDOC and how to return values in a desired order made huge differences in the program's useability.  After a few final hours of playing around, I ended up with a program that ran cleanly, accounted for user errors like mispellings or bad inputs, and displayed an attractive, easy-to-read output that I was very happy with:

![](http://i67.tinypic.com/ir3uqu.png)

In summary, this was a great project.  It taught me a lot and made me feel MUCH more confident at building code.  It also gave me a starting point for building out a real first app.  Next step will be adding additional functionality and using concepts I learn in future lessons to build on this and turn it into a fun, useable, and shareable app!!
