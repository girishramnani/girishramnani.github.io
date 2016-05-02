---
layout: post
title:  "Python Essentials part 1"
subtitle: "lists and io"
date:   2016-01-22 16:57:00
categories: [ python ]
---

This is the tutorial series for python which will contain essential parts of the language.
So lets begin.

Python is a **weakly** typed programming language, that means you dont need to declare the data type of any variables.

## The fundamentals

The variables

{% highlight python %}

i = 5  #integer

j = 5.5 #float

k = "i love python" #string

li = [1,2,3,4,5] # array or known as list in python

{% endhighlight %}

Basic input output

{% highlight python %}

print("hello world") # prints hello world and goes to the next line

word = input("enter a number") # takes input from the user ,and storing it into the word as a string

type(word)  # string.

#to convert the word into other types

int_word = int(word)

float_word = float(word)

list_word = list(word)  #but be aware if the you try to convert string to an int, it would give an error

str_word = str(word)

 {% endhighlight %}

## Lists

Lists are collection of obects with sequential integers as key to access them. lists in python are dynamic so you dont need to specify the size of them.

the methods provided by a list are

{% highlight python %}

li = ["work","eat","sleep",12,1.5,["google","twitter"]] # lists can contain anything from integers to other objects.

li.append("hey")  #to add an element to the end of the list

del(li[0])   # will delete the first element of the list

#the access can be done using negative numbers as well

print(li[-1])    # will print the last element of the list

li.pop()           # to remove the last element , also pop takes an argument of the index to remove

{% endhighlight %}
