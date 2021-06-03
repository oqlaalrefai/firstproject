## operators 

**types of operators:**
1- Assignment operators
+ assigns a value to its left operand (=)
+ Addition assignment	x += y	
+ Subtraction assignment	x -= y	
+ Multiplication assignment	x *= y	 
+ Division assignment	x /= y	
+ Remainder assignment	x %= y	
+ Exponentiation assignment	x **= y	
+ Left shift assignment	x <<= y	
+ Right shift assignment	x >>= y	
+ Unsigned right shift assignment	x >>>= y
+ Bitwise AND assignment	x &= y	
+ Bitwise XOR assignment	x ^= y	
+ Bitwise OR assignment	x |= y	
+ Logical AND assignment	x &&= y	
+ Logical OR assignment	x ||= y	
+ Logical nullish assignment	x ??= y

The return value matches the expression to the right of the = sign

2- Comparison operators
A comparison operator compares its operands and returns a logical value 
Equal (==)Not equal (!=) Strict equal (===)Strict not equal (!==)Greater than (>) Greater than or equal (>=) Less than (<)
Less than or equal (<=)
3- Arithmetic operators
The standard arithmetic operators are addition (+), subtraction (-), multiplication (*), and division (/)
Remainder (%)Increment (++)Decrement (--)Unary negation (-)Unary plus (+)Exponentiation operator (**)

4- Bitwise operators
	Bitwise AND	a & b	
	Bitwise OR	a | b	
	Bitwise XOR	a ^ b
	Bitwise NOT	~ a
	Left shift	a << b	
	Sign-propagating right shift	a >> b	
	Zero-fill right shift	a >>> b

5- Logical operators
	Logical AND (&&)
	Logical OR (||)
	Logical NOT (!)
6- String operators
	 the concatenation operator (+) concatenates two 		string values together,The shorthand 		assignment operator += can also be used to 		concatenate strings.
7- Conditional (ternary) operator
	takes three operands The operator can have one of two 	values based on a condition. The syntax:
	condition ? val1 : val2 If condition is true, the 	operator has the value of val1. Otherwise it has the 	value of val2.
8- Comma operator

9- Unary operators
	delete
	typeof operator returns a string indicating the type 
	The void operator specifies an expression to be 	evaluated without returning a value
	
10- Relational operators
	-The in operator returns true if the specified 	property is in the specified object
	-The instanceof operator returns true if the specified 	object is of the specified object type
	
#### Operator precedence :
	The precedence of operators determines the order they 	are applied when evaluating an expression
	member	. []
	call / create instance	() new

JavaScript has both binary and unary operators, and one special ternary operator, the conditional operator.
A binary operator requires two operands, one before the operator and one after the operator

A unary operator requires a single operand, either before or after the operator:


**this** refers to the calling object in a method.

**Grouping operator**
The grouping operator ( ) controls the precedence of evaluation in expressions

**new**
You can use the new operator to create an instance of a user-defined object type or of one of the built-in object types

**super**
The super keyword is used to call functions on an object's parent. It is useful with classes

## Loops and iteration
Loops offer a quick and easy way to do something repeatedly.

The statements for loops provided in JavaScript are:

1- **for statement** :A for loop repeats until a specified condition evaluates to false
for ([initialExpression]; [conditionExpression]; [incrementExpression])
  {statement}

2- **do...while statement** : The do...while statement repeats until a specified condition evaluates to false.
syntax :
do
  statement
while (condition);
*statement is always executed once before the condition is checked*


3- **while statement** :A while statement executes its statements as long as a specified condition evaluates to true
syntax :
while (condition)
 { statement}
If the condition becomes false, statement within the loop stops executing and control passes to the statement following the loop.

4- **labeled statement** :A label provides a statement with an identifier that lets you refer to it elsewhere in your program.
you can use a label to identify a loop, and then use the break or continue statements to indicate whether a program should interrupt the loop or continue its execution.
syntax :
label :
   statement

5- **break statement** :Use the break statement to terminate a loop, switch, or in conjunction with a labeled statement.


6- **continue statement** :The continue statement can be used to restart a while, do-while, for, or label statement.

7- **for...in statement** :The for...in statement iterates a specified variable over all the enumerable properties of an object.
syntax :
for (variable in object)
  statement

8- for...of statement :The for...of statement creates a loop Iterating over iterable objects (including Array, Map, Set, arguments object and so on), invoking a custom iteration hook with statements to be executed for the value of each distinct property.





