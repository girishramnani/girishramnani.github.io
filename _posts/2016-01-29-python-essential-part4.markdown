---
layout: post
title:  "Python Essentials part 4"
subtitle: "classes"
date:   2016-01-29 16:57:00
categories: [ python ]
---

# Classes

Classes are use to encapsulate data and increase readability as well as design quality of the code.

{% highlight python %}

class Person:
    def __init__(self,first_name,last_name):
        self.first_name =first_name
        self.last_name = last_name

    def get_fullname(self):
        return "{} {}".format(self.first_name,self.last_name)


girish = Person("Girish","Ramnani")
print(girish.get_fullname())   ## Girish Ramnani

{% endhighlight %}

The `__init__` here is the constructor of the object which is called when
`Person("Girish","Ramnani")` is used.
So here there is a `person` class has a method called `get_fullname` and some other attributes.
The first thing that observe is the `self` argument present as the first argument of all instance methods.
for classes in python the first argument of a method is actually the object or the class itself.
so it can be easily understood like this
{% highlight python %}
    girish.get_fullname()
      |
      ----------------------------> Person.get_fullname(girish)
      {% endhighlight %}

Also the code `Person.get_fullname(girish)` will actually give the same result.
All the variables having the `self`(its not compulsary to call it `self`,but its a convention followed
by the community) as their parent will be accessible through other methods of the class.

For more curious ones , the reason for such `self` syntax can be due to two reasons.
<ul>
    <li>It provides a differentiation between instance variables and function scope variables</li>
    <li>The C language doesnt have a object structure so it relies on `struct` for the encapsulation (`struct` cannot contain methods) . So the main structure is passed in each and every method for access of instance variables .
    </li>
</ul>


