# Understanding the JavaScript Call Stack


### What is a ‘call’?
 is primarily used for function invocation (call). Since the call stack is single, function(s) execution, is done, one at a time, from top to bottom.

### How many ‘calls’ can happen at once?
one call at a time

### What does LIFO mean?
A data structure principle. This is the basic understanding of the call stack. Last In, First Out. The last function to go in, the first to come out.

### Draw an example of a call stack and the functions that would need to be invoked to generate that call stack.
```function greets(){
console.log("greeets");
}

function test(){
greets();
console.log("test func");
}

test();```


### What causes a Stack Overflow?
rcursive function
meaning a function that calls itself but does not have an exiting point,The browser (hosting environment) has a maximum stack call that it can accomodate before throwing a stack error.

# JavaScript error messages



### What is a ‘refrence error’?
undeclared variable.

### What is a ‘syntax error’?
this occurs when you have something that cannot be parsed in terms of syntax
ex :
invalid object that you are trying to parse in a JSON file

### What is a ‘range error’?
 give it an invalid length
 ex :
 trying to return a negative position in an array will throw this error.

### What is a ‘tyep error’?
data type (string, number, boolean, ...) in not compatible. Like trying to access a property of variable that doesn't exist.

### What is a breakpoint?
The point were we will have the error

### What does the word ‘debugger’ do in your code?
achieve The breakpoint by putting `debugger` in the line you want to break.
