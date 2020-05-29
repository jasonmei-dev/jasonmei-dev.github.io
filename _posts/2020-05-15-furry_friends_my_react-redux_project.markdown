---
layout: post
title:      "React/Redux Project Snapshot - Petfinder API"
date:       2020-05-15 22:43:54 -0400
permalink:  furry_friends_my_react-redux_project
---


For my final project, I made a pet adoption application called Furry Friends. The application utilized the Petfinder API to access real pet data to allow the user to search through adoptable pets. The user can also view a pet’s details and contact information, add/delete a pet from their profile, and edit their personal information. For the purposes of this post, I will be discussing one of the trickier issues I encountered during my build, which was actually using an external API in conjunction with my Rails backend, and how it tied back to my React front-end.

To use the Petfinder API, you need to first create an account with Petfinder. Afterwards, you are given your client id and client secret which is used to request an access token. This access token is required in the headers of your HTTP requests to the API. Everything was pretty straight-forward at this point. The caveat however, was that this access token expired after an hour. In order to handle this, I decided to make my HTTP requests to the Petfinder API in my Rails backend instead of React, using the `rest-client` gem. I wrote a private controller action `get_token` that is run before all actions in my `pets_controller`. This way, I was requesting a new access token every time I make a HTTP request to Petfinder, ensuring that my access token would never expire. The response from Petfinder API is then sent from Rails to my React front-end.

```
REACT
----------------------------------------------------------------
import { loadingPets, getPets } from '../actions/petfinder';

export const fetchPets = (page=1) => {
  return dispatch => {
    dispatch(loadingPets());
    fetch("http://localhost:3001/api/v1/pets", {
      credentials: "include",
      headers: {
        "Content-Type": "application/json",
        page
      }
    })
    .then(response => response.json())
    .then(pets => dispatch(getPets(pets.animals)))
    .catch(console.log)
  }
}
```

```
RAILS
----------------------------------------------------------------
class Api::V1::PetsController < ApplicationController
  require 'rest-client'
  before_action :get_token

  def index
    page = request.headers[:page]
    url = "https://api.petfinder.com/v2/animals?location=#{current_user.postcode}&sort=distance&page=#{page}"
    headers = { Authorization: "#{@token["token_type"]} #{@token["access_token"]}" }

    response = RestClient.get(url, headers)

    render json: response
  end
	
	private

  def get_token
    url = "https://api.petfinder.com/v2/oauth2/token"

    payload = {
      grant_type: 'client_credentials',
      client_id: ENV['CLIENT_ID'],
      client_secret: ENV['CLIENT_SECRET']
    }

    response = RestClient.post(url, payload)
    @token = JSON.parse(response)
  end
end
```

This may not be the most eloquent way of handling an API's expiring access token, but it is the solution I came up with at the time of building out my project. There are definitely improvements to be made. For example, my `get_token` action isn't the most efficient since I'm requesting a new token on every single HTTP request. A more efficient method would probably be setting up some sort of timer that only requests a new token if an hour has past.

I hope you found the information I shared here helpful and if you want to check out my full project, the repo can be cloned here: [Furry Friends](https://github.com/jmei403/furry-friends-frontend) :)






