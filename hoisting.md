# Hoisting

     By literal meaning, hoisting means to raise or lift something using a tool.

## Hoisting in Javascript

Loosely speaking, hoisting in javascript means that the variable and function declarations are moved to top of the context. But how it is done is that the variable and function declarations are put into memory during the compile time. Hence even if you access a variable before it was
declared we can still access them. Here's an example

```js
     hello();
    function hello() {
        console.log("Hello world");     
        console.log(x);
        var x = 11;
        console.log(x);     
    }
```

This is the output for the above example

    Hello world
    undefined
    11

So by analyzing the output.

* By definition of hoisting, the variable and function declarations referenced at compile time, hence as the program executes and calls `hello()` mehod it knows where the method is declared below in our code.

* Notice the first `console.log(x)` prints **undefined**. This is because hoisting only hoist the variable decalrations to top of the context not the initializations. Initialization only happens at the point where you initialize the variable. So you can see the value **11** is printed on the second `console.log(x)` as the varibale `x` is just initialized above.

## An Important point

* `let` and `const` declarations are an exception to hoisting. You must declare them before accessing. The below example will throw  reference error.

```js
    console.log(num);
    let num  = 100;
```

## References

 [MDN documentation for hoisting](https://developer.mozilla.org/en-US/docs/Glossary/Hoisting)

