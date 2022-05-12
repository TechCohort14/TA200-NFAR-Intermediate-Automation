# Selecting Elements Review

[Code Challenge](https://www.codewars.com/kata/5b37a50642b27ebf2e000010/train/javascript)

Throughout this course you will be able to complete tests and exercises with the following test site: [http://the-internet.herokuapp.com/](http://the-internet.herokuapp.com/)

Take a moment to review the links and familiarize yourself with the user interface that we will use to practice creating tests.

---

## Setup Webdriver

1). Create a new folder

```sh
mkdir selectingElementsReview
```

2). Change directory into the new folder:

```sh
cd selectingElementsReview
```

3). Install web driver.io.

```sh
npm init wdio .
```

4). Select the default for all options.

---

## Commit your work

1). Initialize a version control (git) for your project

```sh
git init
```

2). Open VS Code, create a `.gitignore` file, and add `node_modules` to it.

3). Add your initial files

```sh
git add .
git commit -m "adds initial files"
```

---

## Skip Default Test

1). Place an `x` before the `it` for the login test.

2). Run the test.

```sh
npm run wdio
```

The login test should be skipped.

---

## Assignment

You will define some [selectors](https://webdriver.io/docs/selectors/) and create a few tests using them. You must use at least 3 selector strategies (i.e., ```id attribute``` ```tag name``` ```element with certain text```)

### Steps

1. Create a file in the ```pageobjects``` folder called ```checkboxes.page.js```.

2. Define selectors for the ```heading``` and ```checkbox 2```.

3. Create a file in the ```specs``` folder called ```checkboxes.spec.js```.

4. Create an assertion that states that the ```heading``` [exists](https://webdriver.io/docs/api/expect-webdriverio).

5. Create a test that clicks checkbox 2, and pauses for 2 seconds.

6. Create a file in the ```pageobjects``` folder called ```dropdown.page.js```.

7. Define a selectors for the ```dropdown``` button.

8. Create a file in the ```specs``` folder called ```dropdown.spec.js```.

9. Create a test that clicks the dropdown, button and pauses for 2 seconds.

---

Exit Criteria.

1. Must use the [Page Object Pattern](https://webdriver.io/docs/pageobjects/)
2. Must use 3 different selector strategies.

Bonus

*Use the [xPath selector stategy](https://webdriver.io/docs/selectors/#xpath).*
*Use selenium grid*
