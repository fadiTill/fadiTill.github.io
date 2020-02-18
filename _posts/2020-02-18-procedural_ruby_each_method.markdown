---
layout: post
title:      "Procedural Ruby : Each method."
date:       2020-02-18 15:26:44 -0500
permalink:  procedural_ruby_each_method
---


![](https://images.app.goo.gl/HNAt4CKjNE83FPgeAp://)


Each is an iteration method. Iterations allow you to work on each element of your array, without having to write manually and repeating your code. It is your best friend, it saves you time and is syntax sugar. There is a different way of iterate like map method. I will focus on each because I think it can be confusing. 

 2)  1) Each is like having a box full of blue jumbo lego box.

  array_small_box = [ blue, blue, blue ]

 2) imagine you want to take each blue lego and add a red lego attached to it. 


array_small_box.each do |bluelego| bluelego + “redlego”

3) your old box won’t feet anymore… so you need to take the content of your old box and put it in a new box so that fit.

big_new_box = [ ] .

big_new_box << array_small_box

Now your blue and red lego fits in the new box!
