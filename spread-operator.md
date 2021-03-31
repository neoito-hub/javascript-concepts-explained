### Spread Syntax

Its simple as it sounds, the syntax (...) will spread/expand

```
const a = [1,2,3];
const b = [...a];
// console.log(b) will be [1,2,3]
```

Here ``const a`` was assigned with an iterable expression (array), and its items are copied to ```const b ``` using spread syntax easily. the 3 dots simply expanded/spread whats inside of ```const a```.

Now, I have 3 arrays 

``` 
const arr1 = [1,2,3];
const arr2 = [4,5,6];
const arr3 = [7,8,9];
```
I want to combine these arrays into one, hmm,
```
const combined = [...arr1, ...arr2, ...arr3];
```
will give me
```
[1,2,3,4,5,6,7,8,9]
```
These 3 dots are really powerfull, right?

Lets see if this can work with Objects

```
const myObj = { name: 'Spread' };
```
lets use our 3 dots magic
```
const copied = {...myObj};
// console.log(copied) will be  { name: 'Spread' }
```
Its easy to make a copy/clone of an object now.
I have another object 
```
const myModObj = { age: 5 };
```
Lets combine these to create a new object and add one more  key-value pair
```
const combined = { ...myObj, ...myModObj, score: 100 };
// console.log(combined) will be { name: 'Spread', age: 5, score: 100 }
```

I have a sum function
```
function sum(num1, num2){
	return num1 + num2;
}
```
and an array 
```
const myArray = [3,9];
``` 
instead of 
```
const result = sum(myArray[0], myArray[1])
```
we can use spread syntax.
```
const result = sum(...myArray);
```

You will find this syntax useful going forward...