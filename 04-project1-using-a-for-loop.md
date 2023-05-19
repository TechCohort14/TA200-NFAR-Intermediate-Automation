# Project 01: Using a `for` loop

Throughout this course you will be able to complete tests and exercises with the following test site: [http://the-internet.herokuapp.com/](http://the-internet.herokuapp.com/)

Take a moment to review the links and familiarize yourself with the user interface that we will use to practice creating tests.

For this assignment, we will implement using a `for` loop in our test. We will be testing the [Add/ Remove Elements](http://the-internet.herokuapp.com/add_remove_elements/) page. You may use any outside documentation or refer back to any previous lessons to help you with the synyax.

---

## Setup Webdriver

1). Create a new folder;

```sh
mkdir usingAForLoop
```

2). Change directory into the new folder:

```sh
cd usingAForLoop
```

3). Install web driver.io

```sh
npm init wdio .
```

4). Select the default for all options.

## Commit your work

1). Initialize a version control (git) for your project

```sh
git init
```

2). Open VS Code, create a `.gitignore` file, and add `node_modules` to it.

3). Add your initial files

```sh
git add .
git commit -m "adds tests and folder"
```

---

## Skip Default Test

The most common way to skip tests is to comment them out in the code

1). Place an `x` before the `it` for the login test.

2). Run the test. The login test should be skipped.

---

## Create a test

Let's create a test that goes to the [Add/ Remove Elements](http://the-internet.herokuapp.com/add_remove_elements/) page. Your assignment is to create a `for` loop that clicks the "Add Element" button 5 times.

1). Begin by creating a file in the `page objects` folder called `addremove.page.js`

2). Create the `class`, `selectors`, and anything required to select elements on the 'add/ remove page'. *Use the `login.page` as an example*. You may need to refer to the WebDriverIO docs on creating how to creating selectors [Selectors](https://webdriver.io/docs/selectors/) It may be necessary to use multiple different types of selectors to complete this assignment. When selecting multiple elements, remember to use the [`$$`](https://webdriver.io/docs/api/browser/$$/) syntax.

3). Create your test called `addremove.spec.js`. Use the `example.e2e` file as an example.
*Hint: Choosing the appropriate [assertion](https://webdriver.io/docs/api/expect-webdriverio/#tobeelementsarrayofsize) is key*

---

Exit Criteria.

1). Open the add remove page.

2). Create a `for` loop to click the "Add Element" button 5 times.
   `it('should click the Add Element buttton 5 times', async () => {...`

3). Verify that the elements have been added.
   `it('should haved five "Delete" elements', async () => {...`

4). Create a `for` loop to Delete 2 of the "Delete" elements.
   `it('should delete two "Delete" elements', async () => {...`

5). Verify that only 3 "Delete" elements exists.
   `it('should have only three "Delete" elements remaining', async () => {`

BONUS: Save screenshots after adding buttons and deleting buttons to have further confirmation.
