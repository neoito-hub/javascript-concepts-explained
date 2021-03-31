# Call by value and call by reference in javascript

## Call by value

In call by value when a variable is passed to a function, a new instance of that variable is created and passed onto that function. Hence the original variable will be unaffected from any changes made insdie the function.

Call by value applies to primitive data types in JS. They are **number, string, null, boolean, undefined**.

## Call by reference

In call by reference, when a variable is passed on to a function, its memory reference is passed instead of a new instance. Hence any changes you made to that variable inside that function will also reflects in the original variable(*it's basically the original variable that's being passed :)* &nbsp; ).

Call by reference applies to non primitive data types like **Object and Array**.

## An example

```js
    let num = 11;
    let obj = {a: 1 , b: 2};

    console.log('Before calling foo: ', "num: "num, "obj: "obj);
    foo(num, obj);    
    function foo(num, obj) {
        if (typeof num === 'number') {
            num += 5;
        }
        if(typeof obj === 'object') {
            obj.a = 2;
            obj.b = 1;
        }
        console.log('Inside foo: ', "num: "num, "obj: "obj);
    }

    console.log('After calling foo: ', "num: "num, "obj: "obj);
```

The output for above example is

```
Before calling foo:  num: 11 obj: { a: 1, b: 2 }
Inside foo:  num: 16 obj: { a: 2, b: 1 }
After calling foo:  num: 11 obj: { a: 2, b: 1 }
```

You can see from the output both *num* and *obj* is passed to `foo()`. Since *num* is passed by call by value and *obj* is passed by call by reference, the changes made on *num* is not affected on the original varaible because a new instance is passed, but for the *obj* a reference is passed hence any change made inside the `foo()` is also updated to the *obj* variable outside the function.
