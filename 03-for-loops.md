# EXERCISE 03: For Loops

In this lesson, we will take a look at what JavaScript loops are. We will also go over the syntax and use cases for a For Loop.

---

## What is a Javascript Loop?

Loops provide a quick and easy way to repeatedly run a command.

```javascript
for (let i = 0; i < 6; i++) {
  // Runs 6 times, with values of step 0 through 5.
  console.log('Plus 1');
}

```
In Javascript there are many different kinds of loops however, they all essentially do the same thing: they repeat an action some number of times. (Note that it's possible that number could be zero!)

The various loop mechanisms offer different ways to determine the start and end points of the loop. There are various situations that are more easily served by one type of loop over the others.

The statements for loops provided in JavaScript are:
---

## Basic Grammer

Javascript is case-sensitive, so the variables `fun` and `Fun` are not equal. Instructions in Javascript are called statements and are separated by a semicolon. `(;)`
Writing a semicolon after a statement even when it is not strictly needed, is considered best practice. This reduces the chances of introducing bugs into the code.

**Declarations**

There are 3 types of variable declarations in Javascript, `var`, `let`, `const`.

`var`

Declares a variable, optionally initializing it to a value.

```js
var age = 10;
```
or...

```js
var ages = [];
```

`let`

Declares a block-scoped, local variable, optionally initializing it to a value.

```js
let currentAge =  10;
```

`const`

Declares a block-scoped, read-only named constant.

---

## Variables

Variables are used as symbolic names for values in your application. The names of variables, called "identifiers", conform to certain rules.

JavaScript identifiers must start with a letter, underscore (_), or a dollar sign ($). Subsequent characters can also be digits (0–9).

JavaScript is case-sensitive. It is important to remember that letters include the characters "A" through "Z" (uppercase) as well as "a" through "z" (lowercase).


There are two ways to declare a variable:

-  Using the keyword `var`

```js
var a = 30
```
You can use this syntax to declare both local and global variables, depending on the execution context.


-  Using the keyword `let` or `const`

```js
let b = 10

const c = 12
```

You can use this syntax to declare a block-scope local variable.

A variable is considered a global variable when it is declared outside of any function. It is available to any other code in the current document.

A variable is considered a local variable when it is declared within a function. It is only available within that function.


If a variable is declared without being assigned a value, the value is considered undefined.

Attempting to access an undeclared variable will throw a ReferenceError. 

```js
var n;
console.log('The value of n is equal to' + n); // The value of n is equal to undefined
```

**Constants**

Constants are read-only variables. You can create them using the keyword `const`.

The syntax is the same as `var` and `let`: it must start with a letter, underscore, or a dollar sign ($), and can contain alphabetic, numeric, or underscore characters.

```js
const number = 9;
```

Just like the name implies a constant cannot change value through assignment or be re-declared while the script is running. It must be initialized to a value.

The scope rules for constants are the same as those for `let` block-scope variables. If the   `const` keyword is omitted, the identifier is assumed to represent a variable.

You cannot declare a constant with the same name as a function or variable in the same scope. For example:

```js
// THIS WILL CAUSE AN ERROR
function i() {};
const i = 4;

// THIS WILL ALSO CAUSE AN ERROR
function f() {
  const g = 5;
  var g;

}

```

## Data types

There are eight data types:

*Seven primitive*

1. Boolean -  means either `true` or `false`
2. null - a special keyword denoting a null value (Nothingness).
3. undefined - value is not defined.
4. Number - an integer or floating-point number. For example 42 or 3.14159.
5. Big-Int - an integer with arbitrary precision. For example: 9007199254740992n.
6. String - a sequence of characters that represent a text value. For example: "Hello"
7. Symbol -  a data type whose instances are unique and immutable.
8. Object - you can think of Objects as a named container for values.


Variables and data types go hand in hand. A variable's purpose is to store data. Data types are simply the types of data that can be stored in variables.

Let's take a look at how changing the data type affects our result.

```js
var firstNum = 1;

var secondNum = 5;

var result = firstNum + secondNum;

console.log(result);

// This will log: 6
```

```js
// However if we changed the numbers to strings
var firstNum = "1";

var secondNum = "5";

var result = firstNum + secondNum;

console.log(result);

// This will log: 15
```

Take the [Free Code Camp](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/) training on Basic Javascript to gain a further understanding of topics that we've covered.
