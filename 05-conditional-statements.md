# EXERCISE 05: Conditional Statement

In this lesson, we will take a look conditional statements in Javascript.

---

## Conditional Statements

In JavaScript, when we need to perform an action based on a condition, we use conditional statements.

### `if` Statements

- `if` statement is used to specify a block of code that is to be executed, if a specified condition is true.

**Note:** *Remember that Javascript is case-sensitive. `if` should be in lowercase letters. `If` or `IF` will throw an error.*


```js
if (condition) {
  //  this block of code will be executed if the condition is true
}
```

**Example**

In the example below, if `time` is greater than or equal to `19`, then log `"Good Night"`.

```js
if (time >= 19) {
  console.log("Good Night");
}
```

---

### `else` Statements

- `else` statement is used to specify a block of code that is to be executed if that same specified condition is false.

```js
if (condition) {
  //  this block of code will be executed if the condition is true
} else {
  //  this block of code will be executed if the condition is false
}
```

**Example**

In the example below if `time` is greater than `19` or 7 PM, then the log will be `"Good Night"`. Else it will return `"Good Day"`


```js
if (time > 19) {
  console.log("Good Night");
} else {
  console.log("Good Day");
}
```

---

### `else if` Statements

- `else` statement is used to specify a new condition if the first condition is false.

```js
if (condition #1) {
  //  this block of code will be executed if the condition is true
} else if (condition #2) {
 //    this block of code will be executed if condition #1 is false and condition2 is true
} else {
  //  this block of code will be executed if condition #1 and condition #2 is false
}
```

**Example**

In the example below if `time` is greater than `19` or 7 PM, then the log will be `"Good Night"`. Else it will return 


```js
if (time > 19) {
    console.log("Good Night");
} else if (time < 11){
    console.log("Good Morning")
} else {
  console.log("Good Day");
}
```

---


## Setup Webdriver


1. Create a new folder;

```sh
$ mkdir usingConditionals
```

2. Change directory into the new folder:

```sh
$ cd usingConditionals
```

3. Install web driver.io

```sh
$ npm init wdio .
```

4. Select the default for all options.

## Commit your work

1. Initialize a version control (git) for your project

```sh
git init
```

2. Open VS Code, create a `.gitignore` file, and add `node_modules` to it.

3. Add your initial files

```sh
$ git add .
$ git commit -m "adds tests and folder"
```

---


## Skip Default Test

The most common way to skip tests is to comment them out in the code

1. Place an `x` before the `it` for the login test.

2. Run the test. The login test should be skipped.

---

## Create a test

Let's create a test that goes to the [Checkboxes](http://the-internet.herokuapp.com/checkboxes) page. Your assignment is to use a `if` statement that checks the value of checkbox1 to determine if it is checked or not. If it isn't, the select checkbox 1

1. Begin by creating a file in the `page objects` folder called `checkboxes.page.js`


2. Create the `class`, `selectors`, and anything required to select elements on the 'add/ remove page'. *Use the `login.page` as an example*. You may need to refer to the WebDriverIO docs on creating how to creating selectors [Selectors](https://webdriver.io/docs/selectors/) It may be necessary to use multiple different types of selectors to complete this assignment. 


3. Create your test called `checkboxes.spec.js`. Use the `example.e2e` file as an example. 


---

Exit Criteria.


1. Create an `if` statement. 

2. The condition: is checkbox1 unchecked . 

3. The action: click checkbox1 if the condition is true.



## Bonus

Continue working on the [Free Code Camp](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/) training on Basic Javascript to gain a further understanding of topics that we've covered.











