# Exercise 07: Using a `while` loop

Throughout this course, you will be able to complete tests and exercises with the following test site: [http://the-internet.herokuapp.com/](http://the-internet.herokuapp.com/)


## Review

You might be wondering, since the `for` loop and the `while` loop are so similar, when should you use one over the other. You can use a `while` loop whenever you need to evaluate any type-of expression, as well as when you know how many times a statement is going to be executed.

```js
let example = true;
while (example) {  // evaluates whether the variable is ture
    console.log(example)
    example = false; // redefines the value of the variable and changes it to false
}
```

---

For this assignment, we will implement using a `while` loop in our test. We will be testing the [Dynamically Loaded Page Elements](http://the-internet.herokuapp.com/dynamic_loading/1) page. Use a `while` to logs a message as long as the loading bar is visible on the page.  You may use any outside documentation or refer back to any previous lessons to help you with the syntax.


## Setup Webdriver


1. Create a new folder;

```sh
mkdir usingAWhileLoop
```

2. Change direct ory into the new folder:

```sh
cd usingAWhileLoop
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


1. Begin by creating a file in the `page objects` folder called `dynamically.loaded.page.js`


2. Create the `class`, `selectors`, and anything required to select elements on the 'dynamically loaded page'. *Use the `login.page` as an example*. You may need to refer to the WebDriverIO docs on creating how to creating selectors [Selectors](https://webdriver.io/docs/selectors/) It may be necessary to use multiple different types of selectors to complete this assignment. When selecting multiple elements, remember to use the [`$$`](https://webdriver.io/docs/api/browser/$$/) syntax. 


---

Exit Criteria.

1. Open the dynamically loaded page.

2. Click the "Start" button.

3. Create a `while` loop that logs a  message as long as the loading bar is on the page.  
   

4. The message should read: "the loading bar is currently visible".
   



## Bonus

1. What would you use in webdriver to accomplish the same thing.

2. Set up Selenium Grid

3. Continue working on the [Free Code Camp](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/) training on Basic Javascript to gain a further understanding of topics that we've covered.
