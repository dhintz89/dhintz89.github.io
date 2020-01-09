---
layout: post
title:      "Remembering the User in a SPA"
date:       2019-12-28 15:27:58 -0500
permalink:  passing_the_session_to_an_api
---


When I started my JS with Rails API Project, the first thing I did was create my User Model and set up my login flow in Rails as usual.  Only difference being that this time, I needed to pass the user info into Rails from the frontend JavaScript page and use the returned User info to build a mirroring User Class in JavaScript. This went simply enough and I got my first user created, but when I tried to do anything besides create or login - like show User details or logout for example - I got a 204 No Content error.  A few well placed binding.pry and console.log, along with some time spent researching the issue online, revealed the problem.  The session cookie was not persisting while commands were being passed back and forth between the sides of my website.

More researching got me to a supposed explanation and solution - this was an issue caused by CORS and the solution was to simply add some extra arguments to my Fetch calls to include credentials.  I tried this...and got the same result.  After many hours of researching and trying/failing with different approaches, I decided it was time to reach out for help. My section lead, Ayana, suggested looking into JSON Web Tokens (JWT) and sent me some awesome materials to get me started.

JWTs allow you to pass encoded information, like a UserID in my simple example, from your client browser to your API by including it in the Fetch Request headers.  This lets the **backend assign a unique token** to each user when they either sign up or sign in, and **pass it to the browser** as part of the Fetch Response.  Once created, their browser will **store this token in LocalStorage** using JavaScript's window.localStorage.setItem() method, to be **included in each Fetch Request** using an "Authorization" header.  Once the backend receives this token back, it can try to decode it and, assuming it is successful, **re-authorize the user**.  This will give the effect of "remembering" the user so that only authenticated users can take actions on your Single Page Application.  This [LEARN ARTICLE](http://https://learn.co/lessons/jwt-auth-rails) does an excellent job of walking through the full implementation in a way that is easy to follow and understand, I highly recommend giving it a read if you don't already fully understand JWT.

All in all, a pretty painless fix, although I don't know if I would have arrived at the solution without Ayana's help.  Hopefully this post will help spare a few of my fellow students from scouring the internet looking for a JS-to-Rails Session functionality, and let them skip right to the fun part.
