---
layout: post
title:      "Asynchronous fetch execute cycle explained "
date:       2020-11-20 00:59:39 +0000
permalink:  asynchronous_fetch_execute_cycle_explained
---




**definition**

Fetch is a modern way for  AJAX request and avoid 'callback issues' with the use of promise.
A request is made to the server that interprets the result them update the screen"DOM", so the application can be used while the client program requests Data from the server in the background.
Fetch won't throw an error for a missing URL and will consider it as a complete request, here is why it can be helpful to have 'catch errors'  to filter the responses with a '200' status.


**The conventional flow **

 The first Promise is Pending it will be them "Fulfilled' or 'reject' it will then trigger a .then (call ), it will trigger the catch error if the condition is true,  this chain of event happen asynchronously when the previous promise is complete and resolve as a response.
The response Object has different types available ex Json(), Text(), etc ... to handle the different Data types.

fetch(url)
.then
.then
catch



**example: **

 console.log('a');

        fetch('http://localhost:3000/api/v1/houses')
            .then(resp => {
                 if(resp.status !== 200) {
                     throw new Error(resp.statusText);
                 }
                console.log('b', resp);
                return resp.json();
            })
            .then(data => console.log('c', data))
            .catch(errors => console.log('d', errors))
        
        console.log('e');

**The Flow**
1) in this example  the server will render 'a' first because it read in order from top to bottom
2)  them it will trigger fetch but  the promise will take some times 
3)  so it will  continue his course and render 'e' 
4) then when the data is fetched continue his course to b and finally c.


Fetch is a powerful tool that simplifies AJAX requests.
 
 
 


