---
layout: post
title:      "My Sinatra Workout Tracker"
date:       2019-04-18 21:07:13 -0400
permalink:  my_sinatra_workout_tracker
---


For my second portfolio project I decided to make a workout tracker app that lets you log and track your workouts and share them with others to see.

Rather than building out the app from scratch, I decided to use the Corneal gem to jumpstart my project. Corneal is basically a Sinatra site generator that builds out the skeleton of a Sinatra app with just a few short commands. So instead of worrying about whether your `config.ru` and `Rakefile` are correct, you can just start writing your databases, models, controllers, and views. Corneal is great, and I highly recommend it.

My application has three models: User, Workout, and Exercise. Each user `has_may` workouts, and each workout `belongs_to` a user. Each workout also `has_many` exercises, and each exercise `belongs_to` a workout. 

The rundown of my app is simple. Once you create an account and log in, a user is able to create a new workout on their profile page. Once you create a new workout, that workout will be time-stamped and listed on your profile page. You will then be able to add exercises to that workout. Creating a new exercise allows you to log your sets, reps, and weight for that exercise. You are also given the option to add notes to an exercise for some additional clarity. A user can also delete an exercise from their workout or delete the workout entirely. A user is only able to modify or delete their own workouts/exercises. I also added a User Index page that allows users to look others’ profiles and view their workouts.

While I felt well-prepared with writing the functionality of a basic CRUD app, something I struggled with was styling. I’m just not very comfortable styling a website from scratch yet. Corneal actually has basic styling built-in, but me being overly ambitious decided that I didn’t like what it set me up with, so I tried to redo it myself. It did not go well. Ultimately I found a pretty cool CSS framework called [Bulma](http://bulma.io), and I basically used their documentation to style my app.

Overall I had a fun time working on this project. It’s far from perfect and I already see many things I want to improve and implement, but I’m proud of what I was able to accomplish with everything I’ve learned up to now in the course. This project has not only reinforced what I’ve learned, but it also showed me what I need to improve on (cough cough CSS).

I've rambled on long enough. Thanks for reading if you're still here and if you want to check out my project, the link is below:

[Github Repo](http://github.com/jmei403/sinatra-workout-tracker)

