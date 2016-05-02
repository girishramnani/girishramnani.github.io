---
layout: post
title:  "Python Essentials part 3"
subtitle: "set, lambda and file IO"
date:   2016-01-27 16:57:00
categories: [ python ]
---
Today I am going to show you how to use set,lambda and file IO.

##Set 

Set is a basic data structure which is used for `is in` type of queries and also other some other functionality which are provided by mathematical set.

{% highlight python %}

si = set([1,4,5])
set2 = set([1,4,10])
if 1 in si:
    print(True)    # will take constant time

si.union(set2) # creates a new set having 1,4,5,10


{% endhighlight %}

Similarly there are methods for finding intersection and symmetric difference.


Let me give you a practical example.

{% highlight python %}

patients_who_paid = {"Daniel","James","Lizzy"}

patients_treated = {"Daniel","Ronda","Jason","Mike"}

#get the patients who have to pay

print(patents_treated.difference(patients_who_paid))
# {'Jason', 'Mike', 'Ronda'} need to pay 

#similarly patients who need treatment 
print(patients_who_paid.difference(patients_treated)) 
#  {'James', 'Lizzy'}

# and lastly patients with open accounts (not paid or not treated)

print(patients_treated.symmetric_difference(patients_who_paid)) 

#{'James', 'Jason', 'Lizzy', 'Mike', 'Ronda'}

{% endhighlight %}

There are things that you need to keep in mind while using sets.
1) Sets dont remember the ordering of the elements added.

2) Sets dont support duplicate items. So if you add 2 "Daniel" then the set will only show one.

##Lambda 

Lambda is feature of python which is used to define inline functions.
To show the use case and syntax of lambda function , I will be using methods which we havent seen before.

### sorted

consider a list given below now i want to sort this list on the bases of the second element of the list

`
li = [[1,"girish"],[2,"amit"],[3,"yash"]]
`

so


`sorted(li,key= lambda x:x[1])
`

here you can observe a mapping between a function and a lambda as

`def work(x) : return x[1] => lambda x : x[1]
`

similarly

###filter

`list(filter(lambda x:x >5 ,range(10)))
`
will return a list `[6, 7, 8, 9]`

Points to note about lambda : 

1)lambda functions are anonymous function.

2) they have implied return i.e. you can observe there is no `return` in the lambda function above.


## files

In python, interaction with files is quite syntactically simple.

{% highlight python %}

file = open("file.txt","r")   # here "r" signifies that the file is opened in read mode (can read only)

#ways to get the content from the file

content = file.read()  # reads the whole content in one shot

"""now if you file.read() again you wont get any content as you reached the end of the file (read remembers the
cursor position) .So to go back to the begining of the file use ..

"""

file.seek(0) # 0 is the absolute position of the character

content = file.read(10) # will read first 10 characters

content = file.readline() # to read one line

content = file.readlines() # to read all the lines as a list

#Content can be read use `for in` type of syntax as well 


for line in file:
    print(line)     
    
    """but here keep in mind each line in the file ends with "\n" and print also adds one more so lines will be printed with an extra blank line between them """
                    
# to avoid an extra blank line from printing use .. 

    print(line , end="")  # by default end ="\n" (on windows "\r\n")  that why after every print statement goes to the next line.
    
{% endhighlight %}


Thats all for today. Next time will show you `functions` and `classes`.

