# Function Binding

Are you a fan of `this` operator? I mean, `this` operator is super cool and really useful but sometimes it can make you scared! Like You'll never see it coming. Let's stop being dramatic and carry on the deed.

## Introduction

We are gonna take a look at Function prototypes `bind`, `call` and `apply`. Before we start, Let's recall how `this` operator is useful. 

```js
const human = {
    firstName: 'Phil',
    lastName: 'Coulson',
    fullName: function() {
        return this.firstName + ' ' + this.lastName
    }
};
human.fullName(); // Phil Coulson
```

As you can see here, `fullName` is a property of the object `human`, and it is invoked from `human`. In this case, `this` operator points to the object `human` since it's the context object. So `this.firstName` returns `'Phil'` and similarly for `this.lastName`, '`Coulson`' is returned. Thus the output `'Phil Coulson'` is produced.

Now let's take a look at a situation where `this` can frighten you.

```js
let fullName = human.fullName;
fullName();
```

Can you predict what the output will be? Well, you guessed it right. It won't be `'Phil Coulson'`. Because here, `this` reference is lost. This happens because once the assignment occurs, `human` loses it's context and then for `fullName()`, the global `this` would be the context. Since `firstName` and `lastName` aren't declared in the global context, the output here will

```
undefined undefined
```

So now you understand how `this` can scare you. Believe me, this guide can save hours for you in the future. This one's only a small case. There're bigger challenges while using `this` and you won't even know why your code isn't working. However, javascript has made it easy for us to overcome this situation. The function prototype methods `bind`, `call` and `apply` are your friend. Let's have a look at them one at a time.

**`function.prototype.bind()`** :-

The `bind` prototype takes optional arguments. `bind()` returns an entirely new function, binding the first argument as the `this` context for the function. If no arguments are passed, then the context of the function is set as `null`. Let's see how we can get the output `'Phil Coulson'` in the previous example using the `bind` prototype.

```js
fullName = human.fullName.bind(human) /* returns a new function, binding human as context object for the function, and assigned to fullName */
fullNmae(); // Phil Coulson
```

**`function.prototype.call()` and `function.prototype.apply()`** :-

`call` and `apply` provides a similar functionality as `bind`. The difference is, `call` and `apply` invokes the function after binding the first parameter passed to it as context object, whereas `bind` returns a copy or new function by binding the same as context object. The difference between `call` and `apply` is that `call` accepts more than 2 optional arguments of any type, and `apply` takes atmost 2 arguments, first one being the context object and second one an optional argument, which must be an array.

#### The extra arguments - 
Optional arguments for `bind`, `call` and `apply` are simply the arguments that has to be passed to the function for which these prototypes are called. For `apply`, the second argument is an array of values, which have to be passed to the original function as parameters. 

So, next time when `this` tries to scare you, scare them back ;) . See you on the next section!