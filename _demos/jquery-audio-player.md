---
layout: demo-single
title:  "jQuery Audio Player"
categories: demos
img_path: /img/bloc-jams-demo.png
---
In this demo, I used jQuery to build an audio player. This demonstrates my ability to use and build with jQuery.

You can find the github repo for this here >> [jQuery Audio Player](https://github.com/webdevbrent/bloc-jams-jquery)


## Code walkthrough
In the root directory are several folders. An Assets, scripts and styles folder. There is also an index.html file which is how
the player is viewed within a browser. The assets folder contains the acutal audio files and the albumn covers.

Located in the Scripts folder is the meat and potatoes of the application. There you will find the following files:
album-data.js, album-info.js, helper.js, player-bar.js, player.js, song-list.js. I will attempt to explain each of these files
in depth to prove my knowledge on the subject.

## Album-Data.js
The goal of this script is to provide a fakish api call. As you can see the entire call is assigned to the album variable, which in this case is an object. The object is defined using ES6 syntax 'const'. With ES6 we no longer use 'var' for everything. Instead, we have two new words to use. 'let' and 'const'. 'let' is used when you expect the variables value to change frequently. 'const' is used for more 'constant' variables that you do not expect to change.

{% gist webdevbrent/76eecab7d4a96c1ddfc43b64626df0bd %}

The songs array holds all of the information for each song/track. This data file will be referenced throughout the application.

## Album-Info.js
This file is using jQuery to target specific markup in the page and replace each element with the proper values. It gets the values from the aforementioned album object.

{% gist webdevbrent/81dcc16ba8a66f915eec1848ac052527 %}

I am going to skip over the helper.js and the song-list.js files. These are rather trivial and the player-bar. and player.js files
have a lot more stuff going with them.

## Player.js
This is the MAIN part of the application. The Player class. It is exciting to me that ES6 lets you make a class now. A class is just a  blue print for an object. I will walkthrough this code line by line. Giving line numbers as I go along.

{% gist webdevbrent/9f4e119517b93345e181882ff1dcca02 %}

In line 1 the Player class is defined. 

In lines 2 - 6 is the constructor. What is a constructor? Hmm.. According to [MDN Web docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/constructor)
"The constructor method is a special method for creating and initializing an object created within a class." 
In other words, it sets the initial state for the methods on the class.

In lines 9 - 10 a method named getDuration is defined. It returns the current sound object with the duration.

In lines 13 - 14 a method named getTime is defined. Very similar to get duration except it returns the current time.

In lines 17 - 37 the playPause method is defined. This method takes in a song object and then it is set using the currentlyPlaying method. there are conditional statements that react based on the if a song is playing or not.

The remainder of the file contains several other trivial methods with minor but important functionality.

## Player-Bar.js
This is the majority of the actual jQuery in the application. The Player.js file contained vanilla javascript. This file is all about that jQuery baby!!

{% gist webdevbrent/b4ab0668ade13338f9f13cf479d4254b %}

This is straight forward jQuery. Basically, what I am doing here is targeting some elements on the page. Adding a click event listener and then executing code once the user clicks on that particular element. For example, on line 7, I target the next button. When a user clicks on that button it goes into a first check. That check is asking there is nothing playing then simply return but if there is something playing move on to the next line. Then it runs down to line 12 where another conditional is asking if the the nextSong in the playlist is greater than or equal the total number of songs return nothing. SO what that is really saying is that if you are on the last song and select next then the player should jump back to the first song in the list.