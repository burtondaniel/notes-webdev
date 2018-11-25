## Function Invocation

Reading: https://yehudakatz.com/2011/08/11/understanding-javascript-function-invocation-and-this/


```
function hello(thing) {
  console.log(this + " says hello " + thing);
}

hello.call("Yehuda", "world")
```
this sets the "Yehuda" string as the 'this' in the context of the function.

shorthand call is as follows

```
hello("world");
```

which sets `window` as the context of this in the function, ie:

```
hello.call(window, "world");
```