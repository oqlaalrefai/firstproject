# React lifecycle
React lets you define components as classes or functions. The methods that you are able to use on these are called lifecycle events. These methods can be called during the lifecycle of a component

-Each component in React has a lifecycle which you can monitor and manipulate during its three main phases.
The three phases are: 
  - Mounting : putting elements into the DOM.
  - Updating : A component is updated whenever there is a change in the component's state or props.
  - Unmounting : when a component is removed from the DOM 
  constructor()
The constructor for a React component is called before it is mounted.If the component is a subclass you should call super(props)
- Avoid using this.setState() in the constructor because it can lead to side effects, and it is unnecessary.
- static getDerivedStateFromProps()
This method exists for rare cases where the state relies on changes in props over time.
- componentDidMount()
This method is invoked immediately after a component is mounted. If you need to load anything using a network request or initialize the DOM, it should go here
- getSnapshotBeforeUpdate()
This is another rarely used method that allows you to capture a picture of the DOM to check it before actually changing anything on the DOM.
- shouldComponentUpdate()
Setting shouldComponentUpdate() to false allows you to prevent this from happening. This is in order to optimize performance. If you want to use this method, it may be better to use PureComponent instead, which performs a shallow comparison of props and state
- componentDidUpdate()
This method is useful for performing network requests after a change has occurred.
- componentWillUnmount()
This method allows you to clean up the DOM and netwrok requests/ subscriptions.

- The big difference between props and state is props you pass into a component and state is handled inside of that component and props is handeled outside, we use props to send the parameters and we use state for making changes to that, state is handeled in the component and we can update it inside component while props is handeled outside the component and must be updated outside the component.
- Another thing about props vs state is when you change the state inside of your application it's going to re-render that part of your application whiel props we can't acually change them we need to do it outside.

