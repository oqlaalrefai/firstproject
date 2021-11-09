# Dunder Methods
- called **magic methods**.
special methods are a set of predefined methods you can use to enrich your classes. They are easy to recognize because they start and end with double underscores
 ex:
``__getitem__`` method which allows you to use Python’s list slicing syntax

- Object Initialization: 
  - ``__init__`` :To construct account objects from the Account class I need a constructor
- Object Representation:
  - ``__repr__``: The “official” string representation of an object. This is how you would make an object of the class
  - ``__str__``: The “informal” or nicely printable string representation of an object. This is for the enduser.
- iterarion :
  - __len__ : Returns the number of items in the collection.
  - __getitem__ : Returns an item from the collection by a specified key or  position, this syntax applies to classes similar to dictionaries. If it fails, it should raise KeyError
  - __reversed__ : Returns an inverted iterator for the collection
- Operator Overloading for Comparing Accounts:
  -```
	'__add__'
	'__eq__' 
	'__format__'
	'__ge__'
	'__getattribute__'
	'__getitem__'
	'__getnewargs__'
	'__gt__'
	```
- Callable Python Objects: `__call__`
  - You can make an object callable like a regular function by adding the `__call__` dunder method
- Context Manager Support and the With Statement:
  - **context manager** is a simple “protocol” (or interface) that your object needs to follow so it can be used with the with statement.
  - Basically all you need to do is add __enter__ and __exit__ methods to an object if you want it to function as a context manager.



# Statistics - Probability

- At the most basic level, probability seeks to answer the question, “What is the chance of an event happening?” An event is some outcome of interest. To calculate the chance of an event happening, we also need to consider all the other events that can occur.
We started with descriptive statistics and then connected them to probability. From probability, we developed a way to quantatively show if two groups come from the same distribution. In this case, we compared two wine recommendations and found that they most likely do not come from the same score distribution. In other words, one wine type is most likely better than the other one.

- Statistics doesn’t have to be a field relegated to just statisticians. As a data scientist, having an intuitive understanding on common statistical measures represent will give you an edge on developing your own theories and the ability to subsequently test these theories.

- The normal distribution refers to a particularly important phenomenon in the realm of probability and statistics.

- The normal distribution is significant to probability and statistics thanks to two factors: the Central Limit Theorem and the Three Sigma Rule.

- Z-score : The Z-score is a simple calculation that answers the question, “Given a data point, how many standard deviations is it away from the mean?”



