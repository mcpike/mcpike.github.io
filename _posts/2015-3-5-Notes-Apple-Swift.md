
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

    let name = "Patrick"
    println("My name is \(name)")

#### eval example

    var quantity = 2.0
    var price = 15.0
    println("The total cost is \(quantity * price)")

## Control Flow

### if / if else

### switch


## Looping

### for in

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


### ranges: 1...5  vs.  1..<5

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

    for digit in 1..<5 {
     println(digit)
    }

    /*
    1
    2
    3
    4
    */

### traditional 'for' loop

note: no parens required, nor recommended.  Also, For-In is preferred.


    for var i=0; i < 3; ++i {
      // do something
    } 

### others

while and do-while



## Functions

### declaring functions:

    func myFunction() {
      // do something
    }

### calling functions

    myfunction()

### passing parameters

    func greetPerson(name : String) {
      println("Hello, \(name)")
    }

    greetPerson("Patrick")

    // "Hello, Patrick"


By default parameters are immutable.
In other words, the following code will create an error:

    func willFail(name : String) {
      name = 'foo'  // this will error
    }


### default parameters

    func greetPerson(name : String = "Cool Person!") {
      println("Hello, \(name)")
    }

    greetPerson()
    // "Hello, Cool Person!"
    
    greetPerson("Patrick")
    // ERROR
    
    greetPerson(name: "Patrick")
    // "Hello, Patrick"

### Return values

When returning a value, you must specify the data type of the value that will be returned:

    // This works
    func returnSomething() -> String {
      return "bar"
    }

    // This fails due to wrong return data type 
    func returnSomething() -> Int {
      return "bar"
    }


## Collections

### arrays

Like variables, arrays are typed.

    var shoppingList = ["Eggs", "Milk"]

    shoppingList.append("Flour")

    shoppingList += ["Baking Powder"]


### 
