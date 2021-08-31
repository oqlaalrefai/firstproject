# React Docs - Forms
### What is a *‘Controlled Component’*?
**A controlled component** is a component that renders form elements and controls them by keeping the form data in the component's state.

### Should we wait to store the users responses from the form into state when they submit the form OR should we update the state with their responses as soon as they enter them? Why.
We cant wait untill the user submit the form we need to update the state with their responses as soon as they enter them in input fields, so the updates will runs on every keystroke to update the React state, the displayed value will keep updaing as the user types. And if we waited till the user submits the form the values of the targets will be undifined

### How do we target what the user is entering if we have an event handler on an input field?
The event handler exists on each input field using onChange attribute where the handler itself is using event to target the crossponding input.

# The Conditional (Ternary) Operator Explained
### Why would we use a ternary operator?
we use it for decision making in place of longer if and else conditional statements

### Rewrite the following statement using a ternary statement:
  if(x===y){
 console.log(true);
  } else {
 console.log(false);
  }
sol :
    ```
    x===y ? console.log(true) : console.log(false);
    ```

