---
layout: demo-single
title:  "Simple To-Do List"
categories: demos
img_path: /img/simple-to-do.png
---
In this demo, I used jQuery to build a simple todo list app using jQuery. Visually it is not the most appealing thing but under the hood it has some solid code.

You can find the github repo for this here >> [Simple To Do App](https://github.com/webdevbrent/to-do-app)


## Code walkthrough
This is a very simple two file application. It could even be combined into one but for sanity sake I have chosen to keep it in separate files.


## app.js
The goal of this script is to provide a fakish api call. As you can see the entire call is assigned to the album variable, which in this case is an object. The object is defined using ES6 syntax 'const'. With ES6 we no longer use 'var' for everything. Instead, we have two new words to use. 'let' and 'const'. 'let' is used when you expect the variables value to change frequently. 'const' is used for more 'constant' variables that you do not expect to change.

{% gist webdevbrent/76eecab7d4a96c1ddfc43b64626df0bd %}

The songs array holds all of the information for each song/track. This data file will be referenced throughout the application.

## index.html
This file is using jQuery to target specific markup in the page and replace each element with the proper values. It gets the values from the aforementioned album object.

{% gist webdevbrent/81dcc16ba8a66f915eec1848ac052527 %}

I am going to skip over the helper.js and the song-list.js files. These are rather trivial and the player-bar. and player.js files
have a lot more stuff going with them.
