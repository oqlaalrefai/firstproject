## JS-Basics
Statements should end with a semicolon.
Each of the lines of code in green is a statement
The pink curly braces indicate the start and end of a code block. (Each code block could contain many more statements.)
- JAVASCRIPT IS CASE SENSITIVE
- The semicolon also tells the JavaScript interpreter when a step is over, indicating that it should move to the next step.
- Some statements are surrounded by curly braces; these are known as code blocks.
#### comments
to explain what your code does for single line of comment // your comment for multiple line of comment /* your comment */
#### variable 
A variable is a good name for this concept because the data stored in a variable can change

to dclear a variable 
var x ;
and then you can assign value 
x=20
datatypes :
  - NUMERIC DATA TYPE  x= 7.5
  - STRING DATA TYPE x = 'string '
  - BOOLEAN DATA TYPE (true or false) x = false

you can use scpe character to use the character that you cant use it (/)
x= 'dosen/'t'

- RULES FOR NAMING VARIABLES :
  - The name must begin with a letter, dollar sign ($),or an underscore (_).
  - The name can contain letters,numbers, dollar sign ($), or an underscore (_).
  - You cannot use keywords or reserved words.
  - All variables are case sensitive,
  - Use a name that describes the kind of information that the variable stores.
  - If your variable name is made up of more than one word, use a camelCase
### array :An array is a special type of variable. it stores a list of values
to declear array :
  - var x;
	x=['element1','element2','element3',...]
  - array constructor:
var colors =new Array('white ' ,'black','custom ' );
- Each item in an array is automatically given a number called an index.start from 0
- ACCESSING ITEMS IN AN ARRAY :x[2]; to acces the element that has index number 2
- length holds the number of items in the array
- you can change the value of elemnt inside the array using this technique :
x[2] = 'new value';

### operators 
- ASSIGNMENT OPERATORS
Assign a value to a variable color = 'beige';
- COMPARISON OPERATORS 
<,>,==, !=,====,
- ARITHMETIC OPERATORS
(+ - * /)

# Decission and loops
## decision
decision-making statement which is used to decide whether a block of JavaScript code will execute if a certain condition is true
- its defined which line of code should be run next
- A **flowchart** is a type of diagram that represents a workflow or process 

- there are two component of decission :
  - expression
  - condition statment say what to do
- expression is to us comparission statment using (== ,!= ,=== ,!=== ,< ,> ,>= ,<= 

- COMPARING TWO EXPRESSIONS :
ex: var comparison= (score!+ score2) > (highScorel + highScore2);

### logical operator 
- operators that compare values and return true or false 
logical operators like : 
  - or (||) its return false if both condition is false else it return true
  - and (&&) its return true if both condition is true else it return false
  - not (!) its return the opposite
### Conditional Statements:
#### if
  - if to specify a block of code to be executed, if a specified condition is true
  - else to specify a block of code to be executed, if the same condition is false
  - else if to specify a new condition to test, if the first condition is false 
##### syntax 
if (condition) {
  //  block of code to be executed if the condition is true
}
or if you have multiple cases 
if (condition1) {
  //  block of code to be executed if condition1 is true
} else if (condition2) {
  //  block of code to be executed if the condition1 is false and condition2 is true
} else {
  //  block of code to be executed if the condition1 is false and condition2 is false
}
#### SWITCH STATEMENTS
A switch statement starts with a variable called the switch value. Each case indicates a possible value for this variable and the code that should run if the
variable matches that value.
##### syntax
switch(expression) {
  case x:
    // code block
    break;
  case y:
    // code block
    break;
  default:
    // code block
}

### DATA TYPE PURPOSE
string => Text
number => Number
Boolean => true or false
null  =>  Empty value
undefined => Variable has been declared but not yet assigned a value

**type coercion** : JavaScript can convert data types behind the scenes to complete an operation
**strong typing** :specify what data type each variable will be.
- JavaScript is said to use weak typing because the data type for a value can change.
**unary operator ** returns a result with just one operand.


## loops
if you want to run the same code over and over again, each time with a different value.
- there are three common types of loop:
  - for if you need to run the code specific number of time
syntax:
for (initial state; condition; incrementor decrement) {
  // code block to be executed
}
  - while if you dont know how many times you need to run the code
syntax :
while (condition) {
  // code block to be executed
}
  - do while same as while but the difference it that will run the statement inside barces at least one time even if the condition is false
syntax:
do {
  // code block to be executed
}
while (condition);

### KEY LOOP CONCEPTS:
**break**:This keyword causes the termination of the loop and tells the interpreter to go onto the next statement of code outside of the loop.
**continue**: This keyword te lls the interpreter to continue with the current iteration, and then check the condition again.


























