---
layout: post
title:      "Passing the Session to an API"
date:       2019-12-28 20:27:57 +0000
permalink:  passing_the_session_to_an_api
---


When I started my JS with Rails API Project, the first thing I did was create my User Model and set up my login flow in Rails as usual.  Only difference being that this time, I needed to pass the user info into Rails from the frontend JavaScript page and use the returned User info to build a mirroring User Class in JavaScript. This went simply enough and I got my first user created, but when I tried to do anything besides create or login - like show User details or logout for example - I got a 204 No Content error.  A few well placed binding.pry and console.log, along with some time spent researching the issue online, revealed the problem.  The session cookie was not persisting while commands were being passed back and forth between the sides of my website.

More researching got me to a supposed explanation and solution - this was an issue caused by CORS and the solution was to simply add some extra arguments to my Fetch calls to include credentials.  I tried this...and got the same result.  After many hours of researching and trying/failing different approaches, I decided it was time to reach out for help.



I will edit to add details for the solution once I've figured it out.
