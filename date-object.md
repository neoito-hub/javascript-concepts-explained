# **Date Object**
JavaScript  **`Date`**  objects represent a single moment in time in a platform-independent format.  `Date` objects contain a `Number` that represents milliseconds since 1 January 1970 UTC.

Date objects are created with the  `new Date()`  constructor.

There are  **4 ways**  to create a new date object:

 1. **new Date() ;**

	```
	var d = new Date();
	console.log(d);
	// expected output:
	// Thu Apr 01 2021 20:11:34 GMT+0530 (India Standard Time)
	```
2. **new Date(year, month, day, hours, minutes, seconds, milliseconds);**
	
	`new Date(_year, month, ..._)`  creates a new date object with a  **specified date and time**.

	7 numbers specify year, month, day, hour, minute, second, and millisecond (in that order):
	```
	var d = new Date(2018, 11, 24, 10, 33, 30, 0);
	console.log(d);
	// expected output:
	// Mon Dec 24 2018 10:33:30 GMT+0530 (India Standard Time)
	```
4. **new Date(milliseconds);**

	```
	var d = new Date("October 13, 2014 11:13:00");
	console.log(d);
	// expected output:
	// Mon Oct 13 2014 11:13:00 GMT+0530 (India Standard Time)

	```

4. **new Date(date string);**
	
	```
	var  d =  new  Date(100000000000);
	console.log(d);
	// expected output:
	//Sat Mar 03 1973 15:16:40 GMT+0530 (India Standard Time)

	```
	100000000000 milliseconds from Jan 1, 1970, is approximately Mar 3, 1973:

	
## Date Methods

### Get Methods
Some commonly used get and set methods
| Method | Description |
|--|--|
| getFullYear() | Get the  **year**  as a four digit number (yyyy) |
|getMonth()|Get the **month** as a number (0-11)|
|getDate()|Get the **day** as a number (1-31)|
|getHours()|Get the **hour** (0-23)|
|getMinutes()|Get the **minute** (0-59)|
|getSeconds()|Get the **second** (0-59)|
|getTime()|Get the time (milliseconds since January 1, 1970)|
|Date.now()|Get the time. ECMAScript 5.|

### Set Methods

| Method | Description |
|--|--|
| setDate() | Set the day as a number (1-31) |
|setFullYear()|Set the year (optionally month and day)|
|setHours()|Set the hour (0-23)|
|setMinutes()|Set the minutes (0-59)|
|setTime()|Set the time (milliseconds since January 1, 1970)|



## For more information

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date#

https://www.w3schools.com/js/js_date_methods_set.asp

https://www.w3schools.com/js/js_date_methods.asp

https://www.w3schools.com/js/js_dates.asp