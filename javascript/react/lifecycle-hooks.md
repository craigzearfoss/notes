# React Lifecycle Hooks
- [React.Component](https://reactjs.org/docs/react-component.html)

---

## render()
- The only required method in a class component.
- It should examine this.props and this.state and return one of the following types:
  - **React elements** - Typically created via JSX.
  - **Arrays and fragments** - Lets you return multiple elements from render.
  - **Portals** - Lets you render children into a different DOM subtree.
  - **String and numbers** - These are rendered as text nodes in the DOM.
  - **Booleans or null** - Render nothing.
- It does not modify component state.
- It returns the same result each time it’s invoked.
- It does not directly interact with the browser.
  - If you need to interact with the browser do it in componentDidMount() or the other lifecycle methods.
- It will not be invoked if shouldComponentUpdate() returns false.
- The render method can get called many times. For instance, when anything gets changed.
```
render() {
  return (
    <div>
      Code goes here
    </div>
  );
}
```

## constructor() 
- Called before it is mounted.
- React constructors are typically only used for two purposes:
  - Initializing local state by assigning an object to this.state.
  - Binding event handler methods to an instance.
- **Do not call setState()** in the constructor(). Instead, **assign the initial state to this.state** directly.
- Avoid introducing any side-effects or subscriptions in the constructor. 
  - Use componentDidMount() instead.
  - **Avoid copying props into state!**
```
constructor(props) {
  super(props);
  // Don't call this.setState() here!
  this.state = { counter: 0 };
  this.handleClick = this.handleClick.bind(this);
}
```

## componentDidMount()
- Invoked immediately after a component is mounted (inserted into the tree).
- Initialization that requires DOM nodes should go here.
- If load data from a remote endpoint then instantiate the network request.
- A good place to set up any subscriptions.
  - If you do that, don’t forget to unsubscribe in componentWillUnmount().
- You **may call setState() immediately** in componentDidMount().
  - It triggers an extra rendering, but it will happen before the browser updates the screen. 
  - Use this pattern with caution because it often causes performance issues.
  - In most cases, you should be able to assign the initial state in the constructor().
- The most common use is when you need an api call to get data from an external source.
```
componentDidMount() {
}
```

## componentDidUpdate()
- Invoked immediately after updating occurs.
- Good place to do network requests as long as you compare the current props to previous props.
```
componentDidUpdate(prevProps, prevState, snapshot)
```
- You **may call setState() immediately** in componentDidUpdate() but note that **it must be wrapped in a condition** like in the example below, or you’ll cause an infinite loop.
  - It triggers an extra re-rendering which, but it will not be visible to the user.
  - Use this pattern with caution because it can affect the component performance.
  - If you’re trying to "mirror" some state to a prop coming from above, consider using the prop directly instead. 
- componentDidUpdate() will not be invoked if shouldComponentUpdate() returns false.
```
componentDidUpdate(prevProps) {
  // Typical usage (don't forget to compare props):
  if (this.props.userID !== prevProps.userID) {
    this.fetchData(this.props.userID);
  }
}
```

## componentWillUnmount()

- Invoked immediately before a component is unmounted and destroyed.
- Perform any necessary cleanup for things that were created in componentDidMount(), such as:
  - invalidating timers
  - canceling network requests
  - cleaning up any subscriptions
- **Do not call setState()** in componentWillUnmount() because the component will never be re-rendered.
- Once a component instance is unmounted, it will never be mounted again.
```
componentWillUnmount() {
}
```

---

## shouldComponentUpdate()
- If React ever has a question about whether a component should be re-rendered, it will re-render it just in case.
  - This can become slow in a large app.
```
shouldComponentUpdate(nextProps, nextState) {
  // Return true if you want it to update.
  // Return false if not (Will make the application more performant.)
}
```

## getDerivedStateFromProps()

- Used when the component receives props from its parent and needs to set its own state base on those props.
- Static method.
- Returns the new, updated state based upon the props.
- A lot of times this has been misused and caused weird bugs and performance issues.
  - There's actually a better way to do what they are trying to do.
  - [https://reactjs.org/blog/2018/06/07/you-probably-dont-need-derived-state.html](https://reactjs.org/blog/2018/06/07/you-probably-dont-need-derived-state.html)
- Its use is discouraged.
- [https://reactjs.org/docs/react-component.html#static-getderivedstatefromprops](https://reactjs.org/docs/react-component.html#static-getderivedstatefromprops)

```
static getDerivedStateFromProps(props, state) {
  // return the new, updated state based upon the props
}
```

## getSnapshotBeforeUpdate()

- Allows you to create a backup of the way things are.
- The "snapshot" will most likely be an object with mutliple point of tdata inside of it.
- Not a really common lifecycle method.

```
getSnapshotBeforeUpdate() {
}
```
