---
layout: post
title: Notes on Apple's Swift Language  
tags: swift apple ios 
---

# Notes on Apple's Swift Language

## General Notes

semi-colons are optional, but not recommended.

## Varibles

 - varibles are typed (Int, Double, String, etc.)

 - type inferrence is used when a type is not specified.

### Setting a type

var myVar : Int

let myName : String = "Patrick"


### var vs. let

var: allows for value to be replaced (by the same value type only).

let: defines a constant, the value of which cannot be modified.

let is preferred whenever possible

## Strings

__require__ double quotes


### String Interpolation

    \(expession_to_eval)

#### basic example

{% highlight javascript %}
  let name = "Patrick"
    println("My name is \(name)")
{% endhighlight %}

  

#### eval example

{% highlight javascript %}
    var quantity = 2.0
    var price = 15.0
    println("The total cost is \(quantity * price)")
{% endhighlight %}


 

## Control Flow

### if / if else

### switch


## Looping

### for in

{% highlight javascript %}
    str = "mystring"

    for c in str {
      println(c)
    }

    /*
    m
    y
    s
    t
    r
    i
    n
    g
    */
{% endhighlight %}



### ranges: 1...5  vs.  1..<5

{% highlight javascript %}
  for digit in 1...5 {
        println(digit)
    }

    /*
    1
    2
    3
    4
    5
    */
{% endhighlight %}
  

{% highlight javascript %}
 for digit in 1..<5 {
     println(digit)
    }

    /*
    1
    2
    3
    4
    */
{% endhighlight %}

   

### traditional 'for' loop

note: no parens required, nor recommended.  Also, For-In is preferred.

{% highlight javascript %}
    for var i=0; i < 3; ++i {
      // do something
    } 
{% endhighlight %}


### others

while and do-while


## Functions

### declaring functions:

{% highlight javascript %}
  func myFunction() {
      // do something
    }
{% endhighlight %}
  

### calling functions

{% highlight javascript %}
   func greetPerson(name : String) {
      println("Hello, \(name)")
    }

    greetPerson("Patrick")

    // "Hello, Patrick"

{% endhighlight %}

    myfunction()

### passing parameters

{% highlight javascript %}
   func greetPerson(name : String) {
      println("Hello, \(name)")
    }

    greetPerson("Patrick")

    // "Hello, Patrick"

{% endhighlight %}
 

By default parameters are immutable.
In other words, the following code will create an error:

{% highlight javascript %}
    func willFail(name : String) {
      name = 'foo'  // this will error
    }
{% endhighlight %}



### default parameters

{% highlight javascript %}
  func greetPerson(name : String = "Cool Person!") {
      println("Hello, \(name)")
    }

    greetPerson()
    // "Hello, Cool Person!"
    
    greetPerson("Patrick")
    // ERROR
    
    greetPerson(name: "Patrick")
    // "Hello, Patrick"
{% endhighlight %}

### Return values

When returning a value, you must specify the data type of the value that will be returned:

{% highlight javascript %}
 // This works
    func returnSomething() -> String {
      return "bar"
    }

    // This fails due to wrong return data type 
    func returnSomething() -> Int {
      return "bar"
    }
{% endhighlight %}
   
## Collections

### arrays

Like variables, arrays are typed.

{% highlight javascript %}
var shoppingList = ["Eggs", "Milk"]
shoppingList.append("Flour")
shoppingList += ["Baking Powder"]
{% endhighlight %}
   


### 
