# ES6 Syntax and Feature Overview
- Variable declaration
let keyword, which allows for block-scoped variables which cannot be hoisted or redeclared.`let x = 0`
- Constant declaration
which cannot be redeclared or reassigned, but is not immutable.`const CONST_IDENTIFIER = 0`

- Arrow functions
shorter way of creating a function expression
Arrow functions do not have their own this, do not have prototypes, cannot be used for constructors, and should not be used as object methods.
`let func = (a) => {}`


- Template literals
Concatenation/string interpolation
`var str = 'Release date: ' + date`
`let str = `Release Date: ${date}`

- Implicit returns
The return keyword is implied and can be omitted if using arrow functions without a block body.

- Key/property shorthand
 shorter notation for assigning properties to variables of the same name.
`var obj = {
  a: a,
  b: b,
}`

- Method definition shorthand
The function keyword can be omitted when assigning methods on an object.

- Destructuring (object matching)
Use curly brackets to assign properties of an object to their own variable.
`
var obj = {a: 1, b: 2, c: 3}
var a = obj.a
var b = obj.b
var c = obj.c
`

- Array iteration (looping)
A more concise syntax has been introduced for iteration through arrays and other iterable objects.

- Default parameters
Functions can be initialized with default parameters, which will be used only if an argument is not invoked through the function.
`var func = function (a, b) {
  b = b === undefined ? 2 : b
  return a + b
}`

- Spread syntax
Spread syntax can be used to expand an array.
`
let arr1 = [1, 2, 3]
let arr2 = ['a', 'b', 'c']
let arr3 = [...arr1, ...arr2]
`

- Classes/constructor functions
the class syntax on top of the prototype-based constructor function.
`
class Func {
  constructor(a, b) {
    this.a = a
    this.b = b
  }

  getSum() {
    return this.a + this.b
  }
}`

- Inheritance
The `extends` keyword creates a subclass.

- Modules - export/import
Modules can be created to export and import code between files.
  - export.js
`export {func, obj, x}`
  - import.js
`import {func, obj, x} from './export.js'`

- Promises/Callbacks
Promises represent the completion of an asynchronous function. They can be used as an alternative to chaining functions.

# React

## React - Hello World

## Knowledge Level Assumptions
React is a JavaScript library, and so we’ll assume you have a basic understanding of the JavaScript language. If you don’t feel very confident, we recommend going through a JavaScript tutorial to check your knowledge level and enable you to follow along this guide without getting lost.


## React - JSX
JSX may remind you of a template language, but it comes with the full power of JavaScript.
React separates concerns with loosely coupled units called “components” that contain both.

- React doesn’t require using JSX, but most people find it helpful as a visual aid when working with UI inside the JavaScript code. It also allows React to show more useful error and warning messages.

## Embedding Expressions in JSX
`
const name = 'Josh Perez';
const element = <h1>Hello, {name}</h1>;

ReactDOM.render(
  element,
  document.getElementById('root')
);
`
JSX expressions become regular JavaScript function calls and evaluate to JavaScript objects.

React.createElement() performs a few checks to help you write bug-free code but essentially it creates an object 

## React - Rendering Elements
An element describes what you want to see on the screen
We call this a “root” DOM node because everything inside it will be managed by React DOM.
To render a React element into a root DOM node, pass both to ReactDOM.render()
`
const element = <h1>Hello, world</h1>;
ReactDOM.render(element, document.getElementById('root'));
`
React elements are immutable. Once you create an element, you can’t change its children or attributes
the only way to update the UI is to create a new element, and pass it to ReactDOM.render().

### React Only Updates What’s Necessary
React DOM compares the element and its children to the previous one, and only applies the DOM updates necessary to bring the DOM to the desired state.


## React - Components & Props
Components let you split the UI into independent, reusable pieces, and think about each piece in isolation. This page provides an introduction to the idea of components. 
Conceptually, components are like JavaScript functions. They accept arbitrary inputs (called “props”) and return React elements describing what should appear on the screen.

### Function and Class Components
- The simplest way to define a component is to write a JavaScript function:

`function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}`

This function is a valid React component because it accepts a single “props” (which stands for properties) object argument with data and returns a React element.

- You can also use an ES6 class to define a component:

`class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}`

### Composing Components
Components can refer to other components in their output. This lets us use the same component abstraction for any level of detail. A button, a form, a dialog, a screen: in React apps, all those are commonly expressed as components.

### Props are Read-Only
Whether you declare a component as a function or a class, it must never modify its own props.
All React components must act like pure functions with respect to their props.


## React - State & Lifecycle
### Converting a Function to a Class
You can convert a function component like Clock to a class in five steps:

1. Create an ES6 class, with the same name, that extends React.Component.
2. Add a single empty method to it called render().
3. Move the body of the function into the render() method.
4. Replace props with this.props in the render() body.
5. Delete the remaining empty function declaration.

### Using State Correctly
There are three things you should know about setState().
- Do Not Modify State Directly
- State Updates May Be Asynchronous
- State Updates are Merged
### The Data Flows Down
Neither parent nor child components can know if a certain component is stateful or stateless, and they shouldn’t care whether it is defined as a function or a class.
This is why state is often called local or encapsulated. It is not accessible to any component other than the one that owns and sets it.
A component may choose to pass its state down as props to its child components

## React - Handling Events
Handling events with React elements is very similar to handling events on DOM elements. There are some syntax differences:

- React events are named using camelCase, rather than lowercase.
- With JSX you pass a function as the event handler, rather than a string.

- Another difference is that you cannot return false to prevent default behavior in React. You must call preventDefault explicitly

- You have to be careful about the meaning of this in JSX callbacks. In JavaScript, class methods are not bound by default. If you forget to bind this.handleClick and pass it to onClick, this will be undefined when the function is actually called.

### Passing Arguments to Event Handlers
Inside a loop, it is common to want to pass an extra parameter to an event handler.

# Tailwind CSS
### Utility-First Fundamentals
- Building complex components from a constrained set of primitive utilities.
- With Tailwind, you style elements by applying pre-existing classes directly in your HTML.
- Using utility classes to build custom designs without writing CSS

ex :
- Tailwind’s flexbox and padding utilities (flex, shrink-0, and p-6) to control the overall card layout
- The max-width and margin utilities (max-w-sm and mx-auto) to constrain the card width and center it horizontally
- The background color, border radius, and box-shadow utilities (bg-white, rounded-xl, and shadow-lg) to style the card’s appearance
- The width and height utilities (w-12 and h-12) to size the logo image
- The space-between utilities (space-x-4) to handle the spacing between the logo and the text
- The font size, text color, and font-weight utilities (text-xl, text-black, font-medium, etc.) to style the card text

- You aren’t wasting energy inventing class names. No more adding silly class names like sidebar-inner-wrapper just to be able to style something, and no more agonizing over the perfect abstract name for something that’s really just a flex container.
- Your CSS stops growing. Using a traditional approach, your CSS files get bigger every time you add a new feature. With utilities, everything is reusable so you rarely need to write new CSS.
- Making changes feels safer. CSS is global and you never know what you’re breaking when you make a change. Classes in your HTML are local, so you can change them without worrying about something else breaking.

### Why not just use inline styles?
But using utility classes has a few important advantages over inline styles:

- Designing with constraints. Using inline styles, every value is a magic number. With utilities, you’re choosing styles from a predefined design system, which makes it much easier to build visually consistent UIs.
- Responsive design. You can’t use media queries in inline styles, but you can use Tailwind’s responsive utilities to build fully responsive interfaces easily.
- Hover, focus, and other states. Inline styles can’t target states like hover or focus, but Tailwind’s state variants make it easy to style those states with utility classes.

### Maintainability concerns
The biggest maintainability concern when using a utility-first approach is managing commonly repeated utility combinations.

This is easily solved by extracting components, usually as template partials or components.

# Next.js
To build a complete web application with React from scratch, there are many important details you need to consider:

- Code has to be bundled using a bundler like webpack and transformed using a compiler like Babel.
- You need to do production optimizations such as code splitting.
- You might want to statically pre-render some pages for performance and SEO. You might also want to use server-side rendering or client-side rendering.
- You might have to write some server-side code to connect your React app to your data store.

### Next.js: The React Framework
the most popular way to build the web
- next is a framework built on top of react that abstracts away some of the complexity while still giving you the flexibility to build scalable react applications so with traditional react applications you can only render on the client side
- and next.js gives you the flexibility to choose on a per page basis whether you want to render on the client or the server or a mix of both this hybrid approach makes it really scalable

- the framework it also allows you to choose which data fetching strategy makes the most sense given your use case 


- Next.js aims to have best-in-class developer experience and many built-in features, such as:
1. An intuitive page-based routing system (with support for dynamic routes)
2. Pre-rendering, both static generation (SSG) and server-side rendering (SSR) are supported on a per-page basis
3. Automatic code splitting for faster page loads
4. Client-side routing with optimized prefetching
5. Built-in CSS and Sass support, and support for any CSS-in-JS library
6. Development environment with Fast Refresh support
7. API routes to build API endpoints with Serverless Functions
8. Fully extendable


















