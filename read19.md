# Error Handling & Debugging

- To find the source of an error, it helps to know how scripts are processed.
## **execution contexts**
- Every statement in a script lives in one of three execution contexts:
1. GLOBAL CONTEXT :Code that is in the script, but not in a function.There is only one global context in any page.
2. FUNCTION CONTEXT:Code that is being run within a function.Each function has its own function context.
3. EVAL CONTEXT :Text is executed like code in an internal function called eval()
- stack :js interpret process one line of code at time when statment need data from another function its stack the new function on top of the current task
Each time a script enters a new execution context, there are two phases of activity:
1. PREPARE
  - The new scope is created
  - Variables, functions, and arguments are created
  - The value of the this keyword is determined 
2. EXECUTE
  - Now it can assign values to variables
  - Reference functions and run their code
  - Execute statements
- Functions in JavaScript are said to have lexical scope. They are linked to the object they were defined within
- If a JavaScript statement generates an error, then it throws an exception.
- Error objects can help you find where your mistakes are and browsers have tools to help you read them.
- ERROR OBJECTS:
1. Syntax Error
2. Ref erenceError
3. EvalError
4. URI Error
5. Type Error
6. RangeError
7. Error : GENERIC ERROR OBJECT
8. NaN :NOT AN ERROR
- there are two things you can do with the errors:
  - DEBUG THE SCRIPT TO FIX ERRORS :track down the source of the error,and fix it.
  - HANDLE ERRORS GRACEFULLY :You can handle errors gracefully using try, catch,throw, and finally statements.
- **Debugging is about deduction**: eliminating potential causes of an error.
- You can pause the execution of a script on any line using ***breakpoints***. Then you can check the va lues stored in variables at that point in time
- If you set multiple breakpoints, you can step through them one-by-one to see where values change and a problem might occur
- You can create a breakpoint in your code using just the debugger keyword. When the developer tools are open, this will automatically create a breakpoint.
- You can also place the debugger keyword within a conditional statement so that it only triggers the breakpoint if the condition is met. This is demonstrated in the code below.
- If you know your code might fail, use try, catch, and finally. Each one is given its own code block.
  - TRY First, you specify the code that you t hink might throw an exception within the try block.
  - CATCH If the try code block throws an exception, catch steps in with an alternative set of code
  - FINALLY The contents of the finally code block will run either way - whether the try block succeeded or failed.
- Here are a selection of practical tips that you can try to use when debugging your scripts:
  - ANOTHER BROWSER
  - ADD NUMBERS
  - STRIP IT BACK
  - EXPLAINING THE CODE
  - SEARCH :ex Stack Overflow
  - CODE PLAYGROUNDS
  - VALIDATION TOOLS
- Here is a list of common errors you might find with your scripts :
  - GO BACK TO BASICS
  - MISSED/ EXTRA CHARACTERS
  - DATA TYPE ISSUES





