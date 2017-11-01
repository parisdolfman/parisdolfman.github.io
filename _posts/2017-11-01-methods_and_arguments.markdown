---
layout: post
title:      "Methods and Arguments"
date:       2017-11-01 19:10:53 +0000
permalink:  methods_and_arguments
---


Methods operate like small machines and what you define is returned to you when called or invoked. There are many different things that can be done with a method. For instance we can create a file called say_this.rb and write
def say_this
  puts "I hope it rains on Sunday."
end
and when we enter say_this into the terminal, what is returned to us is "I hope it rains on Sunday." 
We can add arguments into methods to make them more flexible and dynamic so they aren't hard coded. What this means is that the information passed into the method will return specific information back to us. For example, we can create a file called favorite_colors.rb and write
def favorite_colors(name, color)
  puts "My name is #{name} and my favorite color is #{color}." 
end
When called through favorite_colors(Tom, blue) this will return "My name is Tom and my favorite color is blue." 
When something is defined in our code it can be recalled through string interpolation by #{}. Example:

def words_here
 shade = "beige and grey" 
 puts "Dear, let's paint the rooms #{shade}"
end

When called this will pring "Dear, let's paint the rooms beige and grey." 
 
