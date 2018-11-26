react hooks - useState in function components

context - global variables (used for things like themes, or locales)
accessed via renderprop

```
<ThemeContext.Consumer>
{theme => (

    ... other jsx stuff
    <section className={ theme }>
    ...
)}
</ThemeContext.Consumer>
```

replaced with

`const theme = useContext(ThemeContext);`

then in jsx:

    <section className={ theme }>
    

side effects in a class

in the past, done with lifecycle methods - componentDidUpdate, componentDidMount

relpaced with:

    useEffect(() => document.title = input.target.value)

Can also return a function in a useEffect() call, and this will be called to 'clean up' after an effect (ie. unsubscribe from window events)

definitions can be extracted to functions:

function useWindowWidth() {
    const [width, setWidth] = useState(window.innerWidth);
    useEffect(() => {
        const handleResize = () => this.setWidth(window.innerWidth);
        window.addEventListener('resize', handleResize);
        return () => {
            window.removeEventListener('resize', handleResize);
        };
    });
    return width;
}


