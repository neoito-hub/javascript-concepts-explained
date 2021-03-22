# try ... catch ... finally in Javascript 
Handling exceptions in JS are done inside ***try..catch..finally*** blocks. The statements to be executed are written inside *try* statement. This lets you test a block of code for errors. If Error is thrown, the code inside *catch* is executed. If have to handle something like close a file handler regardless of success or error, you do that in the finally block.

## Syntax

```js
try {
  try_statements
}
catch(exception_var){
  catch_statements
} 
finally {
  finally_statements
}
```

# Why try...catch ?

 

***For exception handling***

When some part of the code can behave abnormally maybe due to dynamic input or unexpected operations    we to handle it. An **exception** is thrown on these cases by the js engine or we can manually **throw** an exception if required.  The ***try*** block is where the notorious statements to execute are written. So the code that needs to be executed when an exception is caught has to be under the ***catch*** function. ***Finally*** executes always after try or catch, this is helpful for cleanup.✌

## Usage

Try block inside `{}` is must.
At least one `catch` or `finally` block must be present.
Nesting of `try` blocks are allowed. The nearest `catch` block will be executed if exception is thrown.
`Finally` block will be executed regardless of whether an exception was thrown or caught.
## Exception identifier

The `e` in  `catch(e)`  contains information about the error. We can compare against known cases like 
`TypeError, RangeError, EvalError` etc. 
```js
try {
  func();
} catch(e) {
  if(e instanceof TypeError) {
    // handle statements
  }
}
```

![image](https://user-images.githubusercontent.com/9291829/111962509-62eb5d00-8b18-11eb-84ea-dfde4a3fd3be.png)
