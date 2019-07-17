---
layout: post
title:      "My Rails Project Journey"
date:       2019-07-16 04:22:04 -0400
permalink:  rails_portfolio_project_fit-buddy
---


For my Rails project, I decided to expand on my Sinatra Workout Tracker and renaming it "Fit-Buddy". The main functionality of my project remains the same: a user is able to create/edit/delete workouts, and within those workouts, you can add/edit/delete exercise_entries. A few of the new features include a third-party login feature through the use of the OmniAuth gem, an index page for all the exercises with the ability to filter by exercise categories, and a user rating system for exercises that is reflected on the exercise’s own show page.

The process of working on this project was a mixed bag. Rails made creating models, controllers, and views a lot easier than with Sinatra because of the Rails generators. I was able to get the CRUD features working pretty quickly. The main issue I ran into however, was when it came to nesting my form for exercise_entries. While I was able to create a new enty with an exercise that already existed in my database, I was having trouble creating a new exercise and a new entry simulataneously. I struggled to figure out why on my own, and my stubbornness to figure it out alone held me back for a few days. I finally scheduled a pair session with the project coach, Dwayne, and when our session failed to find a solution to my problem, he suggested I attend the project office hours the next day that was hosted by the section lead, Jenn.

Honestly, I was skeptical that the study group would be helpful because I figured that there would be multiple students asking for help on their projects, and there wouldn't be enough time to get to everyone. I was pleasantly surprised that not only were we able to solve my problem, but there was adaquate time to get to everyone else who had questions. After that initial project office hour, I ended up attending a few more, and it made the project building experience a lot better. This is a pretty dumb lesson to learn 3 projects into the course, but I never really felt the need to use the office hours until now and I will definitely be taking advantage of this resource in the remaining sections.

This blog post has turned into more of a rambling about my rediscovery of the collaborative resources Flatiron has to offer instead of the features of my project itself, but this was really the big takeaway I got from working on this project. If you're still reading, thanks for your time, and I'll see you in Javascript.
