# Classes and Objects
**Objects** are an encapsulation of variables and functions into a single entity. 
**Classes ** are essentially a template to create your objects
example:
```
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")
``
## Accessing Object Variables and Object Functions
```object = className
object.VariableName
object.fuctionName()```

# Thinking Recursively
Problems can often seem big and scary. But if we keep chipping away at them, more often than not we can break them down into smaller chunks trivial enough to solve This is the essence of thinking recursively
## Recursive Functions in Python
- A recursive function is a function defined in terms of itself via self-referential expressions.the function will continue to call itself and repeat its behavior until some condition is met to return a result
- recursive functions structure:
  - base case 
  - recursive case.
- each recursive call adds a stack frame (containing its execution context) to the call stack until we reach the base case. Then, the stack begins to unwind as each call returns its results
- each recursive call has its own execution context

## Recursive Data Structures in Python
A data structure is recursive if it can be deﬁned in terms of a smaller version of itself. A list is an example of a recursive data structure.
- recursive function’s structure can often be modeled after the definition of the recursive data structure it takes as an input. 


