# EXERCISE 06: While Loops

In this lesson, we will examine the `while` loop in Javascript.

---

## What are `while` loops?

The `while` loop executes a specified statement in a loop, as long as the test condition evaluates to true. Before the statement is executed, the condition is checked.

```javascript
let x = 0;
while (x < 5) {
    x++;
}
console.log(x);
// What will the output be?
```

Remember that in Javascript there are many different kinds of loops however, they all do essentially the same thing, which is to repeat an action a set number of times.

---

## Let's look at syntax

```javascript
while (condition) {
    statement
}
```

`condition`

An expression is evaluated before each iteration through the loop. If this `condition` evaluates to true, the `statement` is executed. When the `condition` evaluates to false, execution continues to the `statement` outside of the `while` loop.


`statement`
An optional statement that will execute as long as the condition evaluates to true. You can use a block statement to execute multiple statements.


---

Let's take a step back to look at what Javascript determines to be `true` and what is `false`.

### Truthy

A **truthy** value is a value that is considered `true` when encountered in a Boolean. (*Remember we covered Booleans when we covered data types*). All values are considered truthy unless they are defined as falsy. This means that, all values are truthy except for the following: `false`, `0`, `-0`, `0n`, `""`, `null`, `undefined`, and `NaN`.

The following are examples of truthy values in JavaScript. These examples are coerced to true in Boolean contexts, and as a result, execute the `while` loop:

```javascript
while (true)
while ("false")
while ("0")
while (new Date())
while (12n)
while (3.14)
while (-3.14)
while (42)
while (-42)
while (Infinity)
while (-Infinity)
while ([])
while ({})

```

#### The logical AND operator, `&&`

In the example below, if the first object is truthy, the logical AND operator returns the second operand:

```js
true && "cat"
// returns "cat"

[] && "cat"
// returns "cat"
```


### Falsy

A falsy (sometimes written falsey) value is a value that is considered false when encountered in a Boolean context.

JavaScript uses type conversion to coerce any value to a Boolean in contexts that require it, such as conditionals and loops.

The following table provides a complete list of JavaScript falsy values:



|  Value             | Description                                                                                     |
|--------------------|:-----------------------------------------------------------------------------------------------:|
| `false`            | False.                                                                                          |
| `0`                | The Number zero. This includes, 0x0, etc., and 0.0.                                             |
| `-0`               | The Number negative zero. This includes, -0x0, etc., and -0.0.                                  | 
| `0n`               | The BigInt zero. This includes 0x0n. There is no BigInt negative zero. The negation of 0n is 0n.| 
| `""`, `''`, ` `` ` | Empty string.                                                                                   | 
| `undefined`        | Not defined. A primitive value.                                                                 | 
| `null`             | Nothingness. The absence of any value.                                                          | 
| `NaN`              | Not a number                                                                                    |


The following are examples of falsy values in JavaScript. These examples are coerced to false in Boolean contexts, and as a  result , does **not** execute the `while` loop:

```javascript

while (false)
while (null)
while (undefined)
while (0)
while (-0)
while (0n)
while (NaN)
while ("")

```

#### The logical AND operator, `&&`

In the example below, if the first object is falsy, that object will be returned.


```js
false && "cat"
// ↪ false

0 && "cat"
// ↪ 0
```


#### The logical OR operator, `||`

The logical OR (`||`) operator checks if a set of operands is true, if and only if one or more of its operands is true. It is typically used with boolean values. However, the `||` operator actually returns the value of one of the specified operands, so if this operator is used with non-Boolean values, it will return a non-Boolean value.

```js
const c = 4;
const d = -3;

console.log(c > 0 || d > 0);
// expected output: true
```

---

## Using a while loops

The following `while` loops iterates as long as `a` is less than 5.

```javascript

let a = 0;
let b = 0;

while (a < 5) {
    a++;
    b += a;

}
```

With each iteration, the loop increments `a` and adds it to `b`. Therefore, `b` and `a` take on the following values:

After the first pass: `a` = 1 and `b` = 1
After the second pass: `a` = 2 and `b` = 3
After the third pass: `a` = 3 and `b` = 6
After the fourth pass: `a` = 3 and `b` = 10
After the fifth pass: `a` = 3 and `b` = 15
Upon completing the fifth pass, the condition a < 5 is no longer true. This results in a termination of the loop.

---

Practice using `while` loops by completing the following exercises.

## Setup


1. Create a new folder;

```sh
mkdir while-loop-exercise
```

2. Change directory into the new folder:

```sh
cd while-loop-exercise
```

3. Create a file called `exercises.js`

4. Begin writing you code to solve complete each exercise.

5. You can run your code by running `node exercise.js` 

6. Comment each exercise after completion, so that it doesn't run when you test the next exercise.

---

## Exercises

1. Write a loop that logs numbers from `1` to `9`

```javascript
let i = 0;

while (i < 10) {
    i++;
    console.log(i)
}
```

2. Write a loop that logs the numbers `9` to `1`.

3. Write a loop that returns that takes the variable `num` which has a value of `10000`, and divide by `2` until `num` is less than `10`. Log each iteration of the loop.

4. Write a while loop that logs the number `1` through `12` but skips the number `3`. You may need to use an `if` statement inside your loop. *There is an easy way to skip a number in a loop. Try to find it.*

5. Write a while loop that logs the number `1` through `12` but skips the number `3` and the number `6`. Use the `logical OR`.

---


Continue working on the [Free Code Camp](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/) training on Basic Javascript to gain a further understanding of topics that we've covered.