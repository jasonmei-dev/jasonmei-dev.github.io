---
layout: post
title:      "Training Wheels Off – My First Project (CLI)"
date:       2018-09-28 03:12:50 +0000
permalink:  training_wheels_off_my_first_project_cli
---


So, I just finished recording the video demo for my CLI gem project, and I gotta say, it feels pretty damn good to be done with it. Building a gem and a Github repo from scratch was the most intimidating thing I had to do so far in the program. Up until now I’ve only dealt with labs, which were already built and laid out for me, so I had no idea where to begin.

I started by going through the resource links provided on the project page in Learn. The walkthrough videos were extremely helpful and I can’t recommend them enough when you start this project. The videos went over how to create a gem and create a Github repo for it, which were basically the main things that I was worried about. Once that was out of the way, I just needed to come up with an idea and start coding.

I decided to base my project on movies and box office numbers because I’ve become quite interested in them over the last few years, and I often find myself checking to see how movies performed in the box office each weekend. Also, I’m one of *those* people who analyze the crap out of movies, so building a gem about movies seemed like a good fit. Naturally, the website I decided to scape was RottenTomatoes.

Now that I had my idea, created the Github repo, and created the skeleton for my gem (using Bundler), it was finally time to start coding. My gem has 3 classes: a CLI class that interacts with the user, a Scraper class that scrapes data from the website and creates new movie objects, and a Movie class that represents movie objects and stores them all in an array. I started with my CLI class, and following Avi’s advice, I wrote out what I wanted my CLI to do in plain English and replaced it with actual methods as I went along. I also created “fake data”, to make sure that my CLI was performing as intended. “Fake data” is just hard-coded strings that are used as a placeholder for the data I will be scraping from the website. Once my CLI class was doing what I wanted with the “fake data”, it was time to scrape RottenTomatoes and get my real data.

Scraping wasn't too difficult to me, but that might only be because the RottenTomatoes website is scrape-friendly. I do suggest reading through [The Bastard's Book of Ruby - Parsing HTML with Nokogiri](http://ruby.bastardsbook.com/chapters/html-parsing/), as it's a very helpful guide to scraping. I also suggest doing a lot testing using `binding.pry`; a lot of my time was spent in pry trying to isolate the data that I wanted. 

After days of debugging and refactoring, I was finally ready to push my gem to [rubygems.org](https://rubygems.org/) and install and run it in the Terminal. So, I created an account on Rubygems and typed in the command `gem push <gem-file-name>`, but I kept getting an error that the gem did not exist. I was confused because, what do you mean the file isn't found? I'm working in it right now. After some futile googling, I scheduled a 1:1 session with a technical instructor and together we found the problem quite quickly, and it was the dumbest thing ever... I never actually built the gem (i.e. creating a .gem file). To do this I just had to type `gem build <filename.gemspec>`, and it generated a .gem file. Now, when I tried to publish the gem, it uploaded without a problem!

Overall I am pleased with how my project turned out. Sure, there are things that I want to tweek and refactor (I've already published 4 versions of my gem at the time of writing this post), but I can always go back to expand its features later. After doing this project I feel more confident in my coding skills, and I look forward to the challenges ahead.

If you want to check out my gem, Box Office CLI, here are the links to the Github repo and the gem page on Rubygems: 
* [Github - Box Office CLI](https://github.com/jmei403/box-office-cli-gem)
* [Rubygems - Box Office CLI](https://rubygems.org/gems/box-office-cli)



