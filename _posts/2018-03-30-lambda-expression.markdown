---
layout: post
title:  "Lambda expression...."
date:   2018-03-31 13:30:00
author: jaehoosu
categories: java
tags: lambda
---

## Rules of this theme and editor.

* Quotes simbolic

`->`
`multi line----------
---------------------'

* Hightlight
{% highlight java %}
TextView textView = (TextView) findViewById(R.id.text_view);
...
{% endhighlight %}

* step rules

** with lambda expression



## Lambda expression
Lambda Expressions are one of the most important.....

### java

( parameters ) -> expression body
( parameters ) -> { expression body }
() -> { expression body }
() -> expression body
...

{% highlight java %}

printPersons(
    roster,
    (Person p) -> p.getGender() == Person.Sex.MALE
        && p.getAge() >= 18
        && p.getAge() <= 25
); 

{% endhighlight %}

  
### C++

[ captures ]( params ) -> ret { body }
[ captures ]( params ) { body }
[ captures ]{ body }

[](){ std::cout << "this is lambda expression" << std::endl; }
 
{% highlight c++ %}
// generic lambda, operator() is a template with two parameters
auto glambda = [](auto a, auto&& b) { return a < b; };
bool b = glambda(3, 3.14); // ok
 
// generic lambda, operator() is a template with one parameter
auto vglambda = [](auto printer) {
    return [=](auto&&... ts) // generic lambda, ts is a parameter pack
    { 
        printer(std::forward<decltype(ts)>(ts)...);
        return [=] { printer(ts...); }; // nullary lambda (takes no parameters)
    };
};
auto p = vglambda([](auto v1, auto v2, auto v3) { std::cout << v1 << v2 << v3; });
auto q = p(1, 'a', 3.14); // outputs 1a3.14
q();  

{% endhighlight %}
