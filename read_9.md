# Functional Programming Concepts

### What is Functional Programming?
a style of building app structure that focuses more on the mathematical functions and less on changing state and mutable items.

### What is a pure function and how do we know if something is a pure function?
zero side effects and must return the same result as the given args.No external object given to the function. We want to set args. directly, not use global scoped variables.

  1- Random number generators make a function impure
  2- If we have a function that has a += 1 counter within, this is impure since it's result is changing. Set the function to always return a value + one and set a counter outside of the function will make it pure as the pure function will always return value + 1.
  3- Pure functions are isolated, stable, sonsistent, etc.

### What are the benefits of a pure function?
  - Easier to test. 
  - Easy to memorize your functions.

### What is immutability?
 something cannot be changed

### What is Referential transparency?
if the functions always returns the same result for the same given input. Easy to memorize your functions.

  - pure function + immutable (variable, object, data) = referential transperency Functions as first class entities - treated as a value, used for data.

  - function is referred to from the constants and vars.
  - pass as param to other funcs.
  - returns as result from outside funcs.


# Node JS Tutorial for Beginners #6 - Modules and require()


### What is a module?
JS file that works like a component, it have some functionality and we call it whenever we need it.

### What does the word ‘require’ do?
it like imports the module file to another file so we can use it.

### How do we bring another module into the file the we are working in?
we use require('module_path') ,the 'module_path' will be the path to module we reqire in the working file.

### What do we have to do to make a module available?
we need to export the functionaliteis that we may use in other files using module.export