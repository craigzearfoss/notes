# React State
[State and Lifecyle](https://reactjs.org/docs/state-and-lifecycle.html)

---

## Do Not Modify State Directly
- Use **setState()**
- The only place where you can assign this.state is the constructor.

```
// Wrong
this.state.comment = 'Hello';

// Correct
this.setState({comment: 'Hello'});
```

## State Updates May Be Asynchronous

- React may batch multiple setState() calls into a single update for performance.
```
// Wrong
this.setState({
  counter: this.state.counter + this.props.increment,
});

// Correct (with an arrow function)
this.setState((state, props) => ({
  counter: state.counter + props.increment
}));

// Correct (with a regular function)
this.setState(function(state, props) {
  return {
    counter: state.counter + props.increment
  };
});
```

## State Updates are Merged
- When you call setState(), React merges the object you provide into the current state.
- Example in the constructor:
```
constructor(props) {
  super(props);
  this.state = {
    posts: [],
    comments: []
  };
}
```
- Examples in a different method:

```
componentDidMount() {
  fetchPosts().then(response => {
    this.setState({
      posts: response.posts
    });
  });

  fetchComments().then(response => {
    this.setState({
      comments: response.comments
    });
  });
}
```

## The Data Flows Down
- State is not accessible to any component other than the one that owns and sets it.
  - It is **local** or **encapsulated**.
- Passing its state down as props to its child component:
```
<h2>It is {this.state.date.toLocaleTimeString()}.</h2>
```
