# Exercise 01: Saving Screenshots

Throughout this course you will be able to complete tests and exercises with the following test site: [http://the-internet.herokuapp.com/](http://the-internet.herokuapp.com/)

Take a moment to review the links and familiarize yourself with the user interface that we will use to practice creating tests.

For this lesson, you will implement saving screenshots. You may use any outside documentation to help you with the syntax. [Screenshots](https://webdriver.io/docs/api/browser/saveScreenshot/)

---

## Setup Webdriver

**You should already have [https://nodejs.org/en/](https://nodejs.org/en/) installed.**

1. Create a new folder;

```sh
mkdir savingScreenShots
```

2). Change directory into the new folder:

```sh
cd savingScreenshots
```

3). Install web driver.io

```sh
npm init wdio .
```

4). Select the default for all options.

## Commit your work

1. Initialize a version control (git) for your project

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

Let's create a test that goes to the [dynamic_loading/2](http://the-internet.herokuapp.com/dynamic_loading/2) page, takes a screenshot, clicks the start button, confirms that the "Hello World" text is visible, and take another screenshot.

1). Begin by creating a file in the `page objects` folder called dynamic_loading.page.js

2). Create the `class`, `selectors`, and anything required to select elements on the 'dynamic_loading page'. *Use the `login.page` as an example*. You may need to refer to the WebDriverIO docs on creating how to creating selectors [Selectors](https://webdriver.io/docs/selectors/)

3). Create your test using the `example.e2e` file as an example. You may need the to refer to the WebdriverIO docs on 'Expects' [Expect](https://webdriver.io/docs/api/expect-webdriverio/#tohavetextcontaining)

---

Exit Criteria.

1. Open the dynamic_loading page.

2. Take a screenshot.

3. Click the start button.

4. Verify that the H4 is visible.

5. Take a second screen shot

## Bonus

* Create a Screenshots folder in the root directory and have a your screenshots go there.
