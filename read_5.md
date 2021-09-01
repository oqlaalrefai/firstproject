# Putting it all together
### How would you break a mock into a component heirarchy?
I draw boxes around every component and subcomponent in the mock and then give them all names.
### What is the single responsibility principle and how does it apply to components?
a component should ideally only do one thing. If it ends up growing, it should be decomposed into smaller subcomponents.
### What does it mean to build a *‘static’* version of your application?
A version that takes your data model and renders the UI but has no interactivity, to build a static version of your app that renders your data model, you’ll want to build components that reuse other components and pass data using props. Don’t use state at all to build this static version, state is reserved only for interactivity, that is, data that changes over time. Since this is a static version of the app, you don’t need it.
### Once you have a static application, what do you need to add?
Identify The Minimal but complete Representation Of UI State, to make your UI interactive, you need to be able to trigger changes to your underlying data model. React achieves this with state.
### What are the three questions you can ask to determine if something is state?
  - Is it passed in from a parent via props? If so, it probably isn’t state.
  - Does it remain unchanged over time? If so, it probably isn’t state.
  - Can you compute it based on any other state or props in your component? If so, it isn’t state.
### How can you identify where state needs to live?
  1- Identify every component that renders something based on that state.
  2- Find a common owner component *a single component above all the components that need the state in the hierarchy*.
  3- Either the common owner or another component higher up in the hierarchy should own the state.
  4- If you can’t find a component where it makes sense to own the state, create a new component solely for holding the state and add it somewhere in the hierarchy above the common owner component.
