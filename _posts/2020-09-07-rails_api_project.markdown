---
layout: post
title:      "Rails API project"
date:       2020-09-07 08:29:33 +0000
permalink:  rails_api_project
---





User story
my User story is to create an Open house application, the user can enter  "guests" object data and instances, associate with  "open houses" Objects.


Backend 
For this API,  I create a front and back end. The back end is handled by rails API gem. Because of separation of concern, it focuses on creating the data that we render into JSON  by adding to the controllers "render json."

def index
 @houses = House.all
 render json: @houses
 end

you can also add a gem called "fast JSON " with a serializer, it will add another layer of key-value pair inside hashes including relationships that make for easy nesting of objects attributes, this gem allows more speed and recommended for application deployment. 

def index
 @houses = House.all
 render json: @houses
 end

 for this API, the backend is centered to the data created by the table and relationships 
to make them accessible by fetch and callback from the front end.

let guestsHTML = guests.map(function(guest) { 
 return`
 <div id="card" class="card">
 <div class="container">
 <h2>${guest.house.address}</h2>
 <ul>
 <li>
 <p> ${guest.name}</p>
 <p hidden>${guest.id}</p>
 <p>${guest.phone_number}</p>
 <p>${guest.address}</p>
 <p> ${guest.email}</p>
 <p>${guest.time_line}</p>
 <p> ${guest.comment}</p>
 </ul>
 <button id="data-guest-id">delete</button>
 </div>
 </div>
 `

the front end.
the front end is created by javascript vanilla, using query selector and event listener to add new objects, retrieve and delete from the Dom following the "the CRUD".

 document.querySelector("#guest-collection").innerHTML+= guestsHTML 
 })
 
 Javascript, is is a  dynamic language that offers a great user experience because of the ajax, it is fun as a developer as you can see the result immediately.
, This project was definitely challenging because of the syntax, scope, and hoisting, but a great experience and a great addition to my coding toolbox.
