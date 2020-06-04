---
layout: post
title:      "My first APPLICATION /MVC"
date:       2020-05-10 22:41:37 -0400
permalink:  my_first_application_mvc
---



I was excited to finally make my first application, I been waiting for this moment for years! 
I had a lot of ideas of things that could be automated, I decided to create an Open House application because of a personal need: as new real estate agent, during Open house, I had to make guests sign, in order to build my pipeline of future clients. 
 However for  practical reasons, my tools were limited, I had the choice between a tablet/phone and a signing sheet, I quickly give up on the signing sheet when  I realized that I wasn't able to read people's writing, most of the time.
 
 Therefore  I used a free application that I found on the app store , unfortunately, it did not have all the labels and forms that I needed, the application had a lot of bugs, I was surprised to not be able to found a better free resource on the market yet...
 
 When I found out that I had to create an app using Sinatra gem I thought of finally making my open house signing sheet MVC,that stand for Models, view, crontroller.

 althought I enjoyed this project, I had different challenges to secure the  data:
 
My application  follow basic functions of a persistent storage "CRUD," so a User can create, read, update and delete a guest only if he created  the guest, I did this  with the help of the associations in my  guest and user models and methods in my Controllers:
 
 a  Guest  "belongs_to :user"
 
  a User "has_many :guests"
	
	
Also I want  to restrict the acces to a particular guest, so  only the user that built the guest could be  able to use          CRUD, in order to do that I had the  method  below to my edit  and  delete methods:
 
 if current_user.id == @guest.user_id

Also I created and  secure the session in my ApplicationController

enable :sessions
 set :session_secret, 'secret' 
 
finally the user need to be login, I used  an helper method that I had to my ApplicationController from where my GuestsController and UsersController will inherite.
 
 helpers do 
     
		 def logged_in?
      !!session[:user_id]
     end
 end
	
	  
I really enjoyed making this app and play around with CSS /HTML, it was a lot of trial and errors to figure the routes and appropriate verb; overall it is a great experience and I can't wait to work on more projects.
 
