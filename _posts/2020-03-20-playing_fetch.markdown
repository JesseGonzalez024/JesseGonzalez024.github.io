---
layout: post
title:      "Playing Fetch"
date:       2020-03-20 22:37:31 -0400
permalink:  playing_fetch
---


Think of a browser, it enables you to visit websites where you can read up on the latest news articles, or retrieve information for an upcoming project. All it takes is the address of a website and you’re there! Browser’s belong to the user. The serves as a bridge to communicate between you and the web.

Even on a social media platform. When we create an account, or when we afterwards decide to change our username for the billionth time to comply with our new edgy personality… that simple function consists of the sending what is known as an “HTTP Request” to a server. 

In terms of web development, we may want to display on our website information/ data that appears on an alternate website. This would imply us sending an “HTTP Request” to our desired web address. And catching it the request.

This complex task of cross information data request and retrieval has been condensed to one JavaScript function: FETCH!

![](https://miro.medium.com/max/1360/1*iCtJkcZZsL1lteMD2tiENA.pnghttp://)

The fetch( ) function is an ASYNC function meaning it happens simultaneously as other bits of our web app remain interactable.

This is made possible thanks to the mysterious EVENT LOOP, which really just sends an ASYNC function back to our web app once the browser is done completing the request. The fact that it’s an ASYNC function is imperative to the user experience on our web app.

Inside the parentheses, we would place the web URL address to our desired API wrapped in quotation marks.

The fetch( ) function retrieves data, returning what is known as a “promise”.

A Promise is a way in JS to handle asynchronous events, meaning it’ll get resolved when the event is over or when the data is retrieved, which in turn contains the response: a Response OBJECT. 

Unfortunately this RESPONSE Object in itself, remains “out of touch” to JavaScript. Meaning that as it stands JavaScript cannot manipulate this stream of data. 

To fix this, the returned bit of data which is an HTTP response object, needs to be converted into a JSON (“JavaScript Object Notation”) Object. We can do this by using the json( ) method which converts the response into a JSON Object meaning we can then manipulate it with JavaScript. 

However, this logic is time sensitive, pending on elements that are out of our direct control as web programers. Because of this, the response needs to be contained by a function that understands it cannot be executed until the response request is, approved or rejected. 

Cue .then( ) method.

The .then( ) method, allows for the continuous thread of asynchronous flow in JavaScript. It accepts as an argument a callback function, or logic referring what to do with the fetch( ) response AFTER it's been completed. Here is where you tell JavaScript to ask the network response to be turned into JSON. Which in turn gets sent back as a secondary promise, meaning we would need a second .then( ) function. 

The final then( ) is where we actually have some JSON passed in. At this point it can actually be manipulated through JavaScript as intended. 

















