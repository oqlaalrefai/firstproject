# In Tests We Trust - TDD with Python
**Unit tests** are some pieces of code to exercise the input, the output and the behaviour of your code. You can write them anytime you want.
**TDD** Test-Driven Development is a strategy to think (and write!) tests first.
  - advantage about TDD is to craft the software design first
- A convention widely used is the AAA: Arrange, Act and Assert.
  - **Arrange**: you need to organize the data needed to execute that piece of code (input);
  - **Act**: here you will execute the code being tested (exercise the behaviour);
  - **Assert**: after executing the code, you will check if the result (output) is the same as you were expecting.
- The cycle is made by three steps:
  - Write a unit test and make it fail (it needs to fail because the feature isn’t there, right? If this test passes, call the Ghostbusters, really)
  - Write the feature and make the test pass! (you can dance after that)
  - Refactor the code — the first version doesn’t need to be the beautiful one (don’t be shy)
**XRP **is a cryptographically secured digital asset with verifiable mathematical properties
# If name equals main
`__name__ == “__main__”:`
anything inside indent will run if the module is runing by terminal ot program
**module** is a file containing Python definitions and statements. The file name is the module name with the suffix .py appended. 
Advantages : 
  - it implies that the module is being run standalone by the user and we can do corresponding appropriate actions.
  - If you import this script as a module in another script, the __name__ is set to the name of the script/module.
  - act as either reusable modules, or as standalone programs.
  - its used to execute some code only if the file was run directly, and not imported.

# Recursion
- The process in which a function calls itself directly or indirectly is called recursion and the corresponding function is called as recursive function. Using recursive algorithm, certain problems can be solved quite easily.
- The idea is to represent a problem in terms of one or more smaller problems, and add one or more base conditions that stop the recursion
- its need more memory and more time 
