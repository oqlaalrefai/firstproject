##**A JavaScript function**
is a block of code designed to perform a particular task.

*A JavaScript function* is executed when "something" invokes it (calls it).

` function myFunction(p1, p2) {`
 `return p1 * p2;   // The function returns the product` `of p1 and p2`
`}`
  - defined with the function keyword, followed by a name, followed by parentheses ()
  - The parentheses may include parameter names separated by commas
  - The code to be executed, by the function, is placed inside curly brackets: {}

  - Function parameters are listed inside the parentheses () in the function definition.

  - Function arguments are the values received by the function when it is invoked.

+ When JavaScript reaches a return statement, the function will stop executing.

+ Functions often compute a return value. The return value is "returned" back to the "caller":



**Function Invocation**
The code inside the function will execute when "something" invokes (calls) the function

**Why Functions?**
You can reuse code: Define the code once, and use it many times.

You can use the same code many times with different arguments, to produce different results.

Using the example above, toCelsius refers to the function object, and toCelsius() refers to the function result.

Such a function can be anonymous; it does not have to have a name.

map function that should receive a function as first argument and an array as second argument.

A method is a function that is a property of an object

Function scope :
a function defined in the global scope can access all variables defined in the global scope. A function defined inside another function can also access all variables defined in its parent function, and any other variables to which the parent function has access.

###Recursion
A function can refer to and call itself. There are three ways for a function to refer to itself:

  - The function's name
  - arguments.callee
  - An in-scope variable that refers to the function
ex :
var foo = function bar() {
   // statements go here
}
Within the function body, the following are all equivalent:

bar()
arguments.callee()
foo()

**Closures**
Closures are one of the most powerful features of JavaScript. JavaScript allows for the nesting of functions and grants the inner function full access to all the variables and functions defined inside the outer function (and all other variables and functions that the outer function has access to).

However, the outer function does not have access to the variables a

