---
layout: post
title:      "Making a Game - My Javascript Project"
date:       2020-01-06 20:46:13 -0500
permalink:  making_a_game_-_my_rails_js_project
---


For my Javascript project, I wanted to try something different from the type of apps shown in the labs and make a game. Making a game was something I always wanted to do and I knew Javascript was a powerful language that would allow me to do just that. I decided to start small and create a keyboard typing game called Keyboard Frenzy. The concept was simple; letters would fall down the game window (like Tetris blocks) and the player would have to type the letter before it reached the bottom of the game window. The letters would appear more frequently as the player's score increased. If a letter fell off the screen, the game ended (no second chances). 

Some of the challenges I encountered in my build was implementing some sort of animation for the falling letters and also implementing user authentication and login since running Rails as an API removes this feature from Rails by default. To handle user authentication, I found two solutions: JSON Web Tokens (JWT) and reenabling Rails sessions and cookies. I decided to use the latter method because it seemed the easiest to implement, and Rails sessions was something I was already familiar with from my Sinatra project. To do this, you just need to add a few lines of code in your Rails backend directory: 

```
RAILS config/application.rb
---------------------------------------------------------------
config.middleware.use ActionDispatch::Cookies
config.middleware.use ActionDispatch::Session::CookieStore, key: '_cookie_name'
```

```
RAIL application_controller.rb
---------------------------------------------------------------
include ::ActionController::Cookies
```

This will allow you to use the session hash like you normally would in a full Ruby on Rails application.

The second problem was handling animation, which wasn't a topic covered in the curriculum. The simplest solution I found to implement this feature was using [CSS animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations). With CSS animations, you are able to set the animation type and timing through your `.css` file.

Overall, I had a lot of fun working on this project and I'm proud of the results so far. The experience of figuring how to write the game rules into the application and play testing was something new and addicting. Currently, the game is pretty basic in features to prevent myself from going down a rabbit hole, and hindering me from "completing" my project for the assessment: a player logs in --> plays game --> high score updates if beaten --> player logs out. I'm excited to go back to this post-graduation and add features I already have planned such as a player leaderboard and even possibly live PvP!

If you want to play the game, it can be found here: [Keyboard Frenzy](https://github.com/jmei403/js-typing-game)


