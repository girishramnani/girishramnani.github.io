---
layout: post
title:  "numpy speed comparision"
subtitle: "use in math calculation"
date:   2015-01-13 16:57:00
---

Python has been adopted by scientific community due its ease of development and also
>you concentrate on the logic rather than the syntax

But what makes python fast in development makes it slow in as a language and in scientific computation that could become an issue.

Thats where numpy comes in.

Lets speed compare

{% highlight python %}


def vec2(n):
    import time
    t= time.time()
    a = range(n**2)
    b=range(n**2)
    c=[]
    for i in range(n**2):

        c.append(a[i]+b[i])

    return time.time()-t
    
{% endhighlight %}



similarly using numpy 

{% highlight python %}

def vec3(n):
    import time
    t= time.time()
    a = range(n**2)
    b=range(n**2)
    c=[a[i]+b[i] for i in range(n**2)]
    return time.time()-t

{% endhighlight %}

now speed compare 

{% highlight python %}
vec2(1000) -> 0.5514s
vec3(1000) -> 0.4823s
{% endhighlight %}

numpy seems to be 40% faster but lets see if we can change something

{% highlight python %}

def vec(n):
    import time
    t = time.time()
    a = np.arange(n**2)
    b= np.arange(n**2)
    c = a+b
  
    return time.time() -t
{% endhighlight %}

{% highlight python %}
vec(1000) -> 0.0019
{% endhighlight %}

this is why you use numpy for mathematic calculations.


