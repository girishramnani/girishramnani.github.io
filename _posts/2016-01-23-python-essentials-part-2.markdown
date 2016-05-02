---
layout: post
title:  "Python Essentials part 2"
subtitle: "loops, conditionals and dictionary"
date:   2016-01-23 16:57:00
categories: [ python ]
---
In this tutorial, I m going to quickly show you use of 
loop, conditions and dictionary.

{% highlight python %}

i=[1,2,3]

if len(i) > 3:
    print("hello")
elif i[1] == 3:
    print("ok")
else:
    print("fine")  #even though the code doesnt make any sense but just for                    the syntax
#for loop
for j in range(3):
    print(j)    # will print from 0 to 2


# i =[1,2,3]
#for each style loop
for j in i:
    print(j) #prints from 1 to 3 

k=0

# while loop
while k<3:
    print(k)
    k+=1

{% endhighlight %}

Python doesnt have a switch .. case like functionality.But there is a 
recipe for achieving such functionality

## Dictionary and set

Dictionary are like list but instead of integers as a key they can use 
any immutable object. **immutable objects are objects which cant be changed after creating**

{% highlight python %}

states = { "gujarat":"gandhinagar","rajasthan":"jaipur","west bengal":"kolkata" }

for key,value in states.items():
    print(key,value)       #  => "gujarat gandhinagar" as so on


print(states["gujarat"])     # if key wont be found then Key error occur.


# you can use
print(states.get("delhi","sorry no capital"))

# which will print "sorry no capital"


{% endhighlight %}
There are other methods as well for dictionary but I encourage you to 
explore from the python's documentation .
Thats all for today. In the next tutorial sets,lambda and file IO will be explored.





