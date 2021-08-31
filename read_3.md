# key
### 1- What does .map() return?
its *render* the all array value or the list of data
### 2- If I want to loop through an array and display each value in JSX, how do I do that in React?
you can use `map()` to render it as array of object
### 3- Each list item needs a unique ____.
Each list item needs a unique key, When not using the key, we’ll be given a warning that a key should be provided for list items. A “key” is a special string attribute you need to include when creating lists of elements.
### 4- What is the purpose of a key?
**Keys** help React identify which items have changed, are added, or are removed. Keys should be given to the elements inside the array to give the elements a stable identity, the best way to pick a key is to use a string that uniquely identifies a list item among its siblings.

|-------------------|

# The Spread Operator
### 1- What is the spread operator?
spread syntax refers to the use of an ellipsis of three dots (…) to expand an iterable object into the list of arguments. The spread operator was added to JavaScript in ES6, just like the rest parameters, which have the same syntax: three magic dots `…`
### 2- List 4 things that the spread operator can do?
  - Adding to state in React
  - Concatenating or combining arrays
  - Combining objects
  - Using Math functions
### 3- Give an example of using the spread operator to combine two arrays?
    `
    const arr1 = [`A`,`B`,`C`]
    const arr2 = [`X`,`Y`,`Z`]
    const totalArr = [...arr1,...arr2] 
    `
### 4- Give an example of using the spread operator to add a new item to an array?
``` const arr = ['x','y','z'] // 3
    const toBeadd = ['a', 'b', ...arr] 
```
### 5- Give an example of using the spread operator to combine two objects into one?
```
const a = {x: "x-data"}
const b = {y: "y-data"}
const xydata = {...a,...b}
```
|------------------------------------|
#

### 1-in the video, what is the first step that the developer does to pass functions between components?
 created a new thing (variable or attribute) to send as a prop to send to the child component
### 2-In your own words, what does the increment function do?
create a variable increase its value each time when press on button then returns the value.
### 3-How can you pass a method from a parent component into a child component?
I can pass the other props inside the component tag, method = {this.method}
### 4-How does the child component invoke a method that was passed to it from a parent component?
I can invoke the passed method like we use props
`this.props.method(parameters);`