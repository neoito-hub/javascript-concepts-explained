# var ...const ...let in Javascript 

It's easy to get confused about the difference between `var`, `let` and `const`. No worries fellow developers, I got your back.

It is important we understand the difference betweeen various scopes in `js`.

## Scopes
- Global Scope
- Local Scope

### Global Scope
- A variable can be defined outside a function and can be used inside a function.

### Local Scope
- The variable defined inside a function cannot be used outside it.


## Var

### Syntax
```js
var varname1 = 'some value'
```

The variable declared using `var` can be scoped globally and locally. It is said to have functional scope.

We can also `alter` / `redeclare` the value of `var` variable if needed.

It is first initialized with the value of undefined while `hoisting`.

`Hoisting` is a JS way to call a variable/function on top of the scope before the code is executed.

Global vars becomes properties of the window object

### Example
```js
function varTest() {
  var a = 1;
  {
    var a = 2;  // redeclare the same variable!
    console.log(a);  // 2
  }
  console.log(a);  // 2
}
```

## Let
### Syntax
```js
let varname1 = 'some value'
```

The variable declared using `let` has block scope. It means that the variable is valid only inside the block and the sub-blocks / `{}` in which it is declared.

### Example
```js
function letTest() {
  let a = 1;
  {
    let a = 2;  // different variable
    console.log(a);  // 2
  }
  console.log(a);  // 1
}
```

## Const
### Syntax
```js
const varname1 = 'some value';
```

Variables declared using `const` is just like let. The only difference is that constants cannot be re-assigned. 

`const` cannot be redeclared in the same block too. But can be redeclared inside sub-blocks.

Also they must be assigned at the time of declaration.

### Examples
```js
const a = 'something';

a = 'something else' // This will give an error
{
    const a = 'something else' 
    console.log(a); // 'something else'
}
console.log(a); // 'something'
````