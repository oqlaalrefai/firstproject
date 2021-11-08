# List Comprehensions
In order to keep your code elegant and readable, it’s recommended that you use Python’s comprehension features
List comprehension is a powerful and concise method for creating lists in Python
- List comprehension methods are an elegant way to create and manage lists. 
- more compact way of creating lists. 
- More flexible than for loops and faster
### syntax
`my_new_list = [ expression for item in list ]`
  - item is the object that the expression will work on.
  - list iterable list of objects to build our new list from.
example :
```
digits = [x for x in range(10)]
print(digits)
```
*Output*
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

# Decorators
decorators wrap a function, modifying its behavior.
Python allows you to use decorators in a simpler way with the @
- They can be reused.
- They can decorate functions with arguments and return values.
- They can use @functools.wraps to look more like the decorated function.
ex :
```
def my_decorator(func):
    def wrapper():
        print("Something is happening before the function is called.")
        func()
        print("Something is happening after the function is called.")
    return wrapper

@my_decorator
def say_whee():
    print("Whee!")
```
### Registering Plugins
Decorators don’t have to wrap the function they’re decorating. They can also simply register that a function exists and return it unwrapped. This can be used, for instance, to create a light-weight plug-in architecture
- The `@register` decorator simply stores a reference to the decorated function in the global PLUGINS dict

### Is the User Logged In
 Flask to set up a /secret web page that should only be visible to users that are logged in or otherwise authenticated
