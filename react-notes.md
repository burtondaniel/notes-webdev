Parent components to maintain state - child components being 'pure' components that derive state

### Function components

Components that only have a render function - no individual state. 
Also don't require a class:


```
class Square extends React.Component {
    render() {
        return (
            <button className="square" onClick={() => this.props.onClick()}>
                {this.props.value}
            </button>
        );
    }
}
```

vs:

```
function Square(props) {
    return (
        <button className="square" onClick={props.onClick}>
            {props.value}
        </button>
    );
}
```

Notice the lack of THIS and the direct function calls (ie. no `()`)