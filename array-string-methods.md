# **Array and string methods**
Javascript contains many methods for arrays and strings to perform various operations. These functions are basically pure functions which we will discuss below.


## Pure Functions

Pure functions are the atomic building blocks in functional programming. They are adored for their simplicity and testability.


A  **pure function**  will have the following properties

-   It depends only on its  **own arguments.**
    
-   It wont try to change variables out of its scope.
    
-   It doesn't produce any  **side effects.**

 **Example:**
`const add = (x, y) => x + y
add(2, 4); // 6 `

The above function add () will only returns a value based on the given parameters, regardless of where/when you call it.

If you pass  `2`  and  `4`, you’ll always get  `6`.

Nothing else affects the output.




## Array Methods

### 1. Filter
The **`filter()`** method **creates a new array** with all elements that pass the test implemented by the provided function.
**`filter()`**  does not mutate the array on which it is called.
**`filter()`**  calls a provided `callback` function once for each element in an array, and constructs a new array.Array elements which do not pass the `callback` test are skipped, and are not included in the new array.

**Example 1**
   ``` 
const words = ['spray', 'limit', 'elite', 'exuberant', 'destruction', 'present'];

const result = words.filter(word => word.length > 6);

console.log(result);
// expected output: Array ["exuberant", "destruction", "present"]
```

**Example 2**

```
function isBigEnough(value) {
  return value >= 10
}

let filtered = [12, 5, 8, 130, 44].filter(isBigEnough)
// filtered is [12, 130, 44]
```
### 2. Map

The **map()** method **creates a new array** populated with the results of calling a provided function on every element in the calling array.
Map calls a provided `callback` function **once for each element** in an array, in order, and constructs a new array from the results.

### [When not to use map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map#when_not_to_use_map "Permalink to When not to use map()")

Since  `map`  builds a new array, using it when you aren't using the returned array is an anti-pattern; use  [`forEach`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)  or  [`for...of`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of)  instead.

You shouldn't be using  `map`  if:

-   you're not using the array it returns; and/or
-   you're not returning a value from the callback.

**Example** 

```
const array1 = [1, 4, 9, 16];

// pass a function to map
const map1 = array1.map(x => x * 2);

console.log(map1);
// expected output: Array [2, 8, 18, 32]


```
### 3. Reduce

The **reduce()** method executes a **reducer** function (that you provide) on each element of the array, resulting in single output value.
The  **reducer**  function takes four arguments:

1.  Accumulator
2.  Current Value
3.  Current Index
4.  Source Array

### [How reduce() works](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce#how_reduce_works "Permalink to How reduce() works")

**Example**
```
let sum = [0, 1, 2, 3].reduce(function (accumulator, currentValue) {
  return accumulator + currentValue
}, 0)
// sum is 6
```


## String Methods

### 1.Concat
The **`concat()`** method concatenates the string arguments to the calling string and returns a new string.

**Example**
```
const str1 = 'Hello';
const str2 = 'World';

console.log(str1.concat(' ', str2));
// expected output: "Hello World"

console.log(str2.concat(', ', str1));
// expected output: "World, Hello"
```
### 2.Match
The **`match()`** method retrieves the result of matching a _string_ against a [regular expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions).

**Example**
```
const paragraph = 'The quick brown fox jumps over the lazy dog. It barked.';
const regex = /[A-Z]/g;
const found = paragraph.match(regex);

console.log(found);
// expected output: Array ["T", "I"]
```
### 3.Replace
The **`replace()`** method returns a new string with some or all matches of a `pattern` replaced by a `replacement`.

**Example**
```
const p = 'The quick brown fox jumps over the lazy dog. If the dog reacted, was it really lazy?';

console.log(p.replace('dog', 'monkey'));
// expected output: "The quick brown fox jumps over the lazy monkey. If the dog reacted, was it really lazy?"
```
### 3.Slice
The **`slice()`** method extracts a section of a string and returns it as a new string, without modifying the original string.

**Example**
```
const str = 'The quick brown fox jumps over the lazy dog.';

console.log(str.slice(31));
// expected output: "the lazy dog."

console.log(str.slice(4, 19));
// expected output: "quick brown fox"

```
### 4.Spit
The **`split()`** method divides a [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) into an ordered list of substrings, puts these substrings into an array, and returns the array.

**Example**
 ```
const str = 'The quick brown fox jumps over the lazy dog.';

const words = str.split(' ');
console.log(words);
// expected output:["The", "quick", "brown", "fox", "jumps", "over", "the", "lazy", "dog."]

```


## For more information

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array

https://vimeo.com/160326750

## CheatSheets

https://dev.to/vincenius/javascript-array-functions-cheatsheet-1c15

https://dev.to/rahxuls/ultimate-javascript-cheatsheet-for-2021-41f6