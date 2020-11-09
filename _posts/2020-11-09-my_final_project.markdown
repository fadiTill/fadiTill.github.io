---
layout: post
title:      "My Final project"
date:       2020-11-09 10:29:11 +0000
permalink:  my_final_project
---




During the Bootcamp, I decide to use the same application in order to fully understand the pros and cons of different languages and similarities.
THE OPEN HOUSE APP is a simple application for real estate agents and for sale by owner(FSBO) to enter data of open houses guests.
this MVC is made of a Rail API backend and React-Redux frontend.

 A/Rail API backend 
the backend is an MVC, and follow the Crud and routes restful convention, also using v1 to allow new versions.

 def create
 @house = House.find(params[:house_id])
 @guest = @house.guests.create(guest_params)
 if @guest.save
 render json: @house
 else
 render json: {error: 'Error creating guest'}
 end 
 end

the MVC use  validations,  and  'gem cors '
 validates :name, :phone_number, :email, presence: true
in order to secure data 

 the MVC  has  2 relationships:

 belongs_to :house
 has_many :guests

the MVC  'serializer' to simplify nested data

class HouseSerializer < ActiveModel::Serializer
 attributes :id, :house_address

 has_many :guests

end

B/React frontend 

 the Frontend uses asynchronous fetch with method 'GET'  and' POST

export function fetchHouses() {
 return(dispatch) => {
 fetch('http://localhost:3000/api/v1/houses')

.then(response => response.json())
.then(houses => dispatch({
type:'FETCH_HOUSES',
payload: houses
}))
 }
}

the frontend uses stateful components and 5  stateless components:
import React from 'react'

const MyHeader = (props) => {
 
 return (
 <div>
 <header>
 <h1 style={{color: "black"}}>Welcome to open House</h1>
 </header>
 </div>
 );
 }


 export default MyHeader


 the front end uses 3 routes:

<Route path='/houses/new' component={HouseInput}/>


this Final project offers a lot of challenges from styling to the usage of Redux. overall a good learning experience.
