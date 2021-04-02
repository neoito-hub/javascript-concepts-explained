# **Sets and Weaksets**
Sets and Weaksets are Javascript build-in objects used for storing values.

## Sets
The **`Set`** object lets you store **unique** values of any type, whether [primitive values](https://developer.mozilla.org/en-US/docs/Glossary/Primitive) or object references.

> There are 7 primitive data types:
> [string](https://developer.mozilla.org/en-US/docs/Glossary/String),
> [number](https://developer.mozilla.org/en-US/docs/Glossary/Number),
> [bigint](https://developer.mozilla.org/en-US/docs/Glossary/BigInt),
> [boolean](https://developer.mozilla.org/en-US/docs/Glossary/Boolean),
> [undefined](https://developer.mozilla.org/en-US/docs/Glossary/undefined),
> [symbol](https://developer.mozilla.org/en-US/docs/Glossary/Symbol),
>  [null](https://developer.mozilla.org/en-US/docs/Glossary/Null).

You can iterate through the elements of a set in insertion order.

> Set is used to create mathematical set operation like uinion,intersection etc

### Set Methods

 1. **Set.add(value)**
	Appends  `value`  to the  `Set`  object. Returns the  `Set`  object with added value.

 2. **Set.clear()**
	Removes all elements from the  `Set`  object.

 3. **Set.delete(value)**
	Removes the element associated to the  `value`  and returns a boolean  whether an element was successfully removed or not.  

 4. **Set.has(value)**
	 Returns a boolean asserting whether an element is present with the given value in the  `Set`  object or not.

**Example usage**
```
const mySet1 = new Set()

mySet1.add(1)           // Set [ 1 ]
mySet1.add(5)           // Set [ 1, 5 ]
mySet1.add(5)           // Set [ 1, 5 ]
mySet1.add('some text') // Set [ 1, 5, 'some text' ]
const o = {a: 1, b: 2}
mySet1.add(o)

mySet1.add({a: 1, b: 2})   // o is referencing a different object, so this is okay

mySet1.has(1)              // true
mySet1.has(3)              // false, since 3 has not been added to the set
mySet1.has(5)              // true
mySet1.has(Math.sqrt(25))  // true
mySet1.has('Some Text'.toLowerCase()) // true
mySet1.has(o)       // true

mySet1.size         // 5

mySet1.delete(5)    // removes 5 from the set
mySet1.has(5)       // false, 5 has been removed

mySet1.size         // 4, since we just removed one value

console.log(mySet1)
// logs Set(4) [ 1, "some text", {…}, {…} ] in Firefox
// logs Set(4) { 1, "some text", {…}, {…} } in Chrome
```
**Set Iteration**
```
// iterate over items in set
// logs the items in the order: 1, "some text", {"a": 1, "b": 2}, {"a": 1, "b": 2}
for (let item of mySet1) console.log(item)

```

### Set Tricks

>You can easily convert a set to an array by using a [`spread operator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax)
```
const array = [...new Set([1, 2, 3, 4])];
console.log(array)
// [1, 2, 3, 4]

```
>Since set only contains unique values it can be used to remove duplicates.

```

const numbers = [2,3,4,4,2,3,3,4,4,5,5,6,6,7,5,32,3,4,5]

console.log([...new Set(numbers)])

// [2, 3, 4, 5, 6, 7, 32]

```
## Weakset

`WeakSet` objects are collections of **objects**. Just as with `Set`, each object in a `WeakSet` may occur only once; all objects in a `WeakSet`'s collection are unique.
The `WeakSet` is weak, meaning references to objects in a `WeakSet` are held weakly.
>This also means that there is no list of current objects stored in the collection. `WeakSets` are not enumerable.
>WeaSets are not Iteratable


### WeakSet Methods

 1. **WeakSet.add(value)**
	Appends  `value`  to the  `WeakSet`  object. Returns the  `WeakSet`  object with added value.

 2. **WeakSet.delete(value)**
	Removes the element associated to the  `value`  and returns a boolean  whether an element was successfully removed or not.  

 3. **WeakSet.has(value)**
	 Returns a boolean asserting whether an element is present with the given value in the  `WeakSet`  object or not.
 
 **Example usage**
		
		const ws = new WeakSet();
		const foo = {};
		const bar = {};
		ws.add(foo);
		ws.add(bar);
		ws.has(foo);    // true
		ws.has(bar);    // true
		ws.delete(foo); // removes foo from the set
		ws.has(foo);    // false, foo has been removed
		ws.has(bar);    // true, bar is retained
		


# Conclusion

-   Sets can store any value. WeakSets are collections of objects only.
-   WeakSet does not have  _size_  property.
-   WeakSet does not have  _clear, keys, values, entries, forEach_  methods.
-   WeakSet is not iterable.
## For more information

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakSet