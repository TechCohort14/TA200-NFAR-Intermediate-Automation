# Exercise 15: Built in Objects Cont

So far we've explored what Javascript's objects are. We also mentioned that JavaScript provides built-in objects. These objects contain properties and methods that can make our lives easier. We covered the Math object and some of it's methods. Let's take a look at the rest of our JavaScript built-in objects.

## Array Object

The Array object, as with arrays in other programming languages, enables storing a collection of multiple items under a single variable name, and has members for performing common array operations.

### Array Description

In JavaScript, arrays are not primitive types, they instead are objects with the following core characteristics:

* Arrays are resizable and can contain a mix of different `data types`. (When those characteristics are undesirable, use typed arrays instead.)
JavaScript arrays are not associative arrays and so, array elements cannot be accessed using strings as indexes, but must be accessed using integers as indexes.
JavaScript arrays are zero-indexed: the first element of an array is at index 0, the second is at index 1, and so on — and the last element is at the value of the array's length property minus 1.
JavaScript array-copy operations create shallow copies. (All standard built-in copy operations with any JavaScript objects create shallow copies, rather than deep copies).

### Array Constructor

```js
Array()
```

Creates a new Array object.

#### Array Instance properties

* Prototype is used to add properties/methods to a constructor function

`Array.prototype.at()`

Returns the array item at the given index. Accepts negative integers, which count back from the last item.

`Array.prototype.concat()`

Returns a new array that is the calling array joined with other array(s) and/or value(s).

`Array.prototype.copyWithin()`

Copies a sequence of array elements within an array.

`Array.prototype.entries()`

Returns a new array iterator object that contains the key/value pairs for each index in an array.

`Array.prototype.every()`

Returns true if every element in the calling array satisfies the testing function.

`Array.prototype.fill()`

Fills all the elements of an array from a start index to an end index with a static value.

`Array.prototype.filter()`

Returns a new array containing all elements of the calling array for which the provided filtering function returns true.

`Array.prototype.find()`

Returns the found element in the calling array, if some element in the array satisfies the testing function, or undefined if not found.

`Array.prototype.findIndex()`

Returns the found index in the calling array, if an element in the array satisfies the testing function, or -1 if not found.

`Array.prototype.flat()`

Returns a new array with all sub-array elements concatenated into it recursively up to the specified depth.

`Array.prototype.flatMap()`

Returns a new array formed by applying a given callback function to each element of the calling array, and then flattening the result by one level.

`Array.prototype.forEach()`

Calls a function for each element in the calling array.

`Array.prototype.groupBy()` Experimental

Groups the elements of an array into an object according to the strings returned by a test function.

`Array.prototype.groupByToMap()` Experimental

Groups the elements of an array into a Map according to values returned by a test function.

`Array.prototype.includes()`

Determines whether the calling array contains a value, returning true or false as appropriate.

`Array.prototype.indexOf()`

Returns the first (least) index at which a given element can be found in the calling array.

`Array.prototype.join()`

Joins all elements of an array into a string.

`Array.prototype.keys()`

Returns a new array iterator that contains the keys for each index in the calling array.

`Array.prototype.lastIndexOf()`

Returns the last (greatest) index at which a given element can be found in the calling array, or -1 if none is found.

`Array.prototype.map()`

Returns a new array containing the results of invoking a function on every element in the calling array.

`Array.prototype.pop()`

Removes the last element from an array and returns that element.

`Array.prototype.push()`

Adds one or more elements to the end of an array, and returns the new length of the array.

`Array.prototype.reduce()`

Executes a user-supplied "reducer" callback function on each element of the array (from left to right), to reduce it to a single value.

`Array.prototype.reduceRight()`

Executes a user-supplied "reducer" callback function on each element of the array (from right to left), to reduce it to a single value.

`Array.prototype.reverse()`

Reverses the order of the elements of an array in place. (First becomes the last, last becomes first.)

`Array.prototype.shift()`

Removes the first element from an array and returns that element.

`Array.prototype.slice()`

Extracts a section of the calling array and returns a new array.

`Array.prototype.some()`

Returns true if at least one element in the calling array satisfies the provided testing function.

`Array.prototype.sort()`

Sorts the elements of an array in place and returns the array.

`Array.prototype.splice()`

Adds and/or removes elements from an array.

`Array.prototype.toLocaleString()`

Returns a localized string representing the calling array and its elements. Overrides the Object.prototype.toLocaleString() method.

`Array.prototype.toString()`

Returns a string representing the calling array and its elements. Overrides the Object.prototype.toString() method.

`Array.prototype.unshift()`

Adds one or more elements to the front of an array, and returns the new length of the array.

`Array.prototype.values()`

Returns a new array iterator object that contains the values for each index in the array.

`Array.prototype[@@iterator]()`

Returns the values() function by default.

#### Creating an Array from an array

```js
// 'cars' array created using array literal notation.
const cars = ['Ford', 'Chevy', 'BMW'];
console.log(cars.length);
// 3

// 'car' array created using the Array() constructor.
const cars = new Array('Ford', 'Chevy', 'BMW');
console.log(cars.length);
// 3
```

### Array exercises

1). Write a JavaScript function to check whether an 'input' is an array or not.

Test Data:
console.log(is_array('helloWorld'));
<!-- should ouput false -->

console.log(is_array([1, 2, 4, 0]));
<!-- should ouput true -->

```js
function is_array(input) {
  if (toString.call(input) === "[object Array]")
    return true;
  return false;   
    };
```

2). Write a simple JavaScript program to join all elements of the following array into a string.
Sample array : myColor = ["Red", "Green", "White", "Black"];

Expected Output:
"Red,Green,White,Black"
"Red,Green,White,Black"
"Red+Green+White+Black"

## Date

An objects represent a single moment in time in a platform-independent format. Date objects contain a Number that represents milliseconds since 1 January 1970 UTC.

### Date Constructor

```js
Date()
```

When called as a function, returns a string representation of the current date and time, exactly as `new Date().toString()` does.

```js
new Date()
```

When called as a constructor, returns a new Date object.

### Date Instance methods

`Date.prototype.getDate()`

Returns the day of the month (1–31) for the specified date according to local time.

`Date.prototype.getDay()`

Returns the day of the week (0–6) for the specified date according to local time.

`Date.prototype.getFullYear()`

Returns the year (4 digits for 4-digit years) of the specified date according to local time.

`Date.prototype.getHours()`

Returns the hour (0–23) in the specified date according to local time.

`Date.prototype.getMilliseconds()`

Returns the milliseconds (0–999) in the specified date according to local time.

`Date.prototype.getMinutes()`

Returns the minutes (0–59) in the specified date according to local time.

`Date.prototype.getMonth()`

Returns the month (0–11) in the specified date according to local time.

`Date.prototype.getSeconds()`

Returns the seconds (0–59) in the specified date according to local time.

`Date.prototype.getTime()`

Returns the numeric value of the specified date as the number of milliseconds since January 1, 1970, 00:00:00 UTC. (Negative values are returned for prior times.)

`Date.prototype.getTimezoneOffset()`

Returns the time-zone offset in minutes for the current locale.

`Date.prototype.getUTCDate()`

Returns the day (date) of the month (1–31) in the specified date according to universal time.

`Date.prototype.getUTCDay()`

Returns the day of the week (0–6) in the specified date according to universal time.

`Date.prototype.getUTCFullYear()`

Returns the year (4 digits for 4-digit years) in the specified date according to universal time.

`Date.prototype.getUTCHours()`

Returns the hours (0–23) in the specified date according to universal time.

`Date.prototype.getUTCMilliseconds()`

Returns the milliseconds (0–999) in the specified date according to universal time.

`Date.prototype.getUTCMinutes()`

Returns the minutes (0–59) in the specified date according to universal time.

`Date.prototype.getUTCMonth()`

Returns the month (0–11) in the specified date according to universal time.

`Date.prototype.getUTCSeconds()`

Returns the seconds (0–59) in the specified date according to universal time.

`Date.prototype.getYear()`

Returns the year (usually 2–3 digits) in the specified date according to local time. Use getFullYear() instead.

`Date.prototype.setDate()`

Sets the day of the month for a specified date according to local time.

`Date.prototype.setFullYear()`

Sets the full year (e.g. 4 digits for 4-digit years) for a specified date according to local time.

`Date.prototype.setHours()`

Sets the hours for a specified date according to local time.

`Date.prototype.setMilliseconds()`

Sets the milliseconds for a specified date according to local time.

`Date.prototype.setMinutes()`

Sets the minutes for a specified date according to local time.

`Date.prototype.setMonth()`
Sets the month for a specified date according to local time.

`Date.prototype.setSeconds()`

Sets the seconds for a specified date according to local time.

`Date.prototype.setTime()`

Sets the Date object to the time represented by a number of milliseconds since January 1, 1970, 00:00:00 UTC. Use negative numbers for times prior.

`Date.prototype.setUTCDate()`

Sets the day of the month for a specified date according to universal time.

`Date.prototype.setUTCFullYear()`

Sets the full year (e.g. 4 digits for 4-digit years) for a specified date according to universal time.

`Date.prototype.setUTCHours()`

Sets the hour for a specified date according to universal time.

`Date.prototype.setUTCMilliseconds()`

Sets the milliseconds for a specified date according to universal time.

`Date.prototype.setUTCMinutes()`

Sets the minutes for a specified date according to universal time.

`Date.prototype.setUTCMonth()`

Sets the month for a specified date according to universal time.

`Date.prototype.setUTCSeconds()`

Sets the seconds for a specified date according to universal time.

`Date.prototype.setYear()`

Sets the year (usually 2–3 digits) for a specified date according to local time. Use setFullYear() instead.

`Date.prototype.toDateString()`

Returns the "date" portion of the Date as a human-readable string like 'Thu Apr 12 2018'.

`Date.prototype.toISOString()`

Converts a date to a string following the ISO 8601 Extended Format.

`Date.prototype.toJSON()`

Returns a string representing the Date using toISOString(). Intended for use by JSON.stringify().

`Date.prototype.toGMTString()`

Returns a string representing the Date based on the GMT (UTC) time zone. Use toUTCString() instead.

`Date.prototype.toLocaleDateString()`

Returns a string with a locality sensitive representation of the date portion of this date based on system settings.

`Date.prototype.toLocaleString()`

Returns a string with a locality-sensitive representation of this date. Overrides the Object.prototype.toLocaleString() method.

`Date.prototype.toLocaleTimeString()`

Returns a string with a locality-sensitive representation of the time portion of this date, based on system settings.

`Date.prototype.toString()`

Returns a string representing the specified Date object. Overrides the Object.prototype.toString() method.

`Date.prototype.toTimeString()`

Returns the "time" portion of the Date as a human-readable string.

`Date.prototype.toUTCString()`

Converts a date to a string using the UTC timezone.

`Date.prototype.valueOf()`

Returns the primitive value of a Date object. Overrides the Object.prototype.valueOf() method.

### JS Date Exercise

1). Write a JavaScript function to check whether an 'input' is a date object or not.

Test Data:

```js
console.log(is_date("April 28, 2022 11:13:00"));
console.log(is_date(new Date(86400000)));
console.log(is_date(new Date(99,5,24,11,33,30,0)));
console.log(is_date([0, 1, 2, 4, 5]));
```
<!-- Output :
false
true
true
false -->

2). Write a JavaScript function to get difference between two dates in days.

Test Data:

```js
console.log(date_diff_indays('04/02/2014', '11/04/2014'));
console.log(date_diff_indays('12/02/2014', '11/04/2014'));
```
<!-- Output :
216
-28 -->

## String

The String object is used to represent and manipulate a sequence of characters.

## String Descreption

Strings are useful for holding data that can be represented in text form. Some of the most-used operations on strings are to check their length, to build and concatenate them using the + and += string operators, checking for the existence or location of substrings with the indexOf() method, or extracting substrings with the substring() method.

### String Constructor

```js
String()

```

### Instance properties

`String.prototype.length`

Reflects the length of the string. Read-only.

Creates a new String object. It performs type conversion when called as a function, rather than as a constructor, which is usually more useful.

### Array Instance methods

`String.prototype.at(index)` Experimental
Returns the character (exactly one UTF-16 code unit) at the specified index. Accepts negative integers, which count back from the last string character.

`String.prototype.charAt(index)`
Returns the character (exactly one UTF-16 code unit) at the specified index.

`String.prototype.charCodeAt(index)`
Returns a number that is the UTF-16 code unit value at the given index.

`String.prototype.codePointAt(pos)`
Returns a nonnegative integer Number that is the code point value of the UTF-16 encoded code point starting at the specified pos.

`String.prototype.concat(str [, ...strN ])`
Combines the text of two (or more) strings and returns a new string.

`String.prototype.includes(searchString [, position])`
Determines whether the calling string contains searchString.

`String.prototype.endsWith(searchString [, length])`
Determines whether a string ends with the characters of the string searchString.

`String.prototype.indexOf(searchValue [, fromIndex])`
Returns the index within the calling String object of the first occurrence of searchValue, or -1 if not found.

`String.prototype.lastIndexOf(searchValue [, fromIndex])`
Returns the index within the calling String object of the last occurrence of searchValue, or -1 if not found.

`String.prototype.localeCompare(compareString [, locales [, options]])`
Returns a number indicating whether the reference string compareString comes before, after, or is equivalent to the given string in sort order.

`String.prototype.match(regexp)`
Used to match regular expression regexp against a string.

`String.prototype.matchAll(regexp)`
Returns an iterator of all regexp's matches.

`String.prototype.normalize([form])`
Returns the Unicode Normalization Form of the calling string value.

`String.prototype.padEnd(targetLength [, padString])`
Pads the current string from the end with a given string and returns a new string of the length targetLength.

`String.prototype.padStart(targetLength [, padString])`
Pads the current string from the start with a given string and returns a new string of the length targetLength.

`String.prototype.repeat(count)`
Returns a string consisting of the elements of the object repeated count times.

`String.prototype.replace(searchFor, replaceWith)`
Used to replace occurrences of searchFor using replaceWith. searchFor may be a string or Regular Expression, and replaceWith may be a string or function.

`String.prototype.replaceAll(searchFor, replaceWith)`
Used to replace all occurrences of searchFor using replaceWith. searchFor may be a string or Regular Expression, and replaceWith may be a string or function.

`String.prototype.search(regexp)`
Search for a match between a regular expression regexp and the calling string.

`String.prototype.slice(beginIndex[, endIndex])`
Extracts a section of a string and returns a new string.

`String.prototype.split([sep [, limit] ])`
Returns an array of strings populated by splitting the calling string at occurrences of the substring sep.

`String.prototype.startsWith(searchString [, length])`
Determines whether the calling string begins with the characters of string searchString.

`String.prototype.substring(indexStart [, indexEnd])`
Returns a new string containing characters of the calling string from (or between) the specified index (or indices).

`String.prototype.toLocaleLowerCase( [locale, ...locales])`
The characters within a string are converted to lowercase while respecting the current locale.

For most languages, this will return the same as toLowerCase().

`String.prototype.toLocaleUpperCase( [locale, ...locales])`
The characters within a string are converted to uppercase while respecting the current locale.

For most languages, this will return the same as toUpperCase().

`String.prototype.toLowerCase()`
Returns the calling string value converted to lowercase.

`String.prototype.toString()`
Returns a string representing the specified object. Overrides the Object.prototype.toString() method.

`String.prototype.toUpperCase()`
Returns the calling string value converted to uppercase.

`String.prototype.trim()`
Trims whitespace from the beginning and end of the string. Part of the ECMAScript 5 standard.

`String.prototype.trimStart()`
Trims whitespace from the beginning of the string.

`String.prototype.trimEnd()`
Trims whitespace from the end of the string.

`String.prototype.valueOf()`
Returns the primitive value of the specified object. Overrides the Object.prototype.valueOf() method.

`String.prototype.@@iterator()`
Returns a new iterator object that iterates over the code points of a String value, returning each code point as a String value.

### JS String Exercise

1). Write a JavaScript function to check whether a string is blank or not.

Test Data :
console.log(is_Blank(''));
<!-- should return true -->

console.log(is_Blank('xyz'));
<!-- should return false -->

2). Write a JavaScript function to check whether an 'input' is a string or not.

Test Data:
console.log(isInputAString('helloWorld'));
<!-- should return true -->
console.log(isInputAString([0, 1, 2, 4, 5]));
<!-- should return false -->

3). Write a JavaScript function to capitalize the first letter of a string.

Test Data :

console.log(capitalize('my string exercises'));
<!-- should return "My string exercises" -->

Complete the [Object Oriented Programming](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/#object-oriented-programming) section of the Free Code Camp Curriculum.
