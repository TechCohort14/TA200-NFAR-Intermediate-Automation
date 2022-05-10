# Exercise 18: Selectors Refersher

The WebDriver Protocol provides several selector strategies to query an element. WebdriverIO simplifies them to keep selecting elements simple.

Throughout this course you will be able to complete tests and exercises with the following test site: [http://the-internet.herokuapp.com/](http://the-internet.herokuapp.com/)

Take a moment to review the links and familiarize yourself with the user interface that we will use to practice creating tests.

---

## Setup Webdriver

**You should already have [https://nodejs.org/en/](https://nodejs.org/en/) installed.**

1). Create a new folder;

```sh
mkdir SelectorsReview
```

2). Change directory into the new folder:

```sh
cd SelectorsReview
```

3). Install web driver.io

```sh
npm init wdio .
```

4). Select the default for all options.

## Commit your work

1). Initialize a version control (git) for your project.

```sh
git init
touch .gitignore
```

2). Open VS Code in the current folder.

```sh
code .
```

3). In VS Code add `node_modules` to your `.gitignore` file.

4). Add your initial files

```sh
git add .
git commit -m "adds initial files"
```

---

## Running your first test

You can start the tests using:

```sh
npm run wdio
```

You should see a browser open, run the tests in a browser, and then the browser will close.

---

## Add a new test

We'll begin by creating a new page object.

The goal when using page objects is to abstract any page information away from the actual tests. Ideally, you should store all selectors or specific instructions that are unique for a certain page in a page object, so that you still can run your test after you've completely redesigned your page.

1). Create a new file in the `test/pageobjects/` folder called `key_presses.page.js`

2). Copy the following into the new file you created:

```js
const Page = require('./page');

/**
 * sub page containing specific selectors and methods for a specific page
 */
class KeyPressesPage extends Page {
    /**
     * define selectors using getter methods
     */
    get keyPressInput() {
         return $('#target');
     }
    /**
     * a method to encapsule automation code to interact with the page
     * e.g. to login using username and password
     */
    //

    /**
     * overwrite specific options to adapt it to page object
     */
    open() {
        return super.open('key_presses');
    }
}

module.exports = new KeyPressesPage();

```

3). Next let's create a new file in the `test/specs/` folder called `key_presses.test.js`

```js
const KeyPressesPage = require('../pageobjects/key_presses.page');

describe('My Key Press application', () => {
    it('visit the key presses page', async () => {
        await KeyPressesPage.open();

        await expect KeyPressesPage.key_presses
    });
});

```

4). Run the tests using

```sh
npm run wdio
```

And you should see the tests fail.

5). Fix the tests by modifying the text to say 'Your password is invalid!' instead of 'You logged into a secure area!'

6). Run the tests, and see that they are still failing, we need to also change the Page Object.

7). In the `test/pageobjects` folder on line 23 add the following to the `login.page.js`.

```js
    get flashAlert() {
        return $('#flash');
    }
```

8). In the `test/specs/` folder update your tests to use the correct page object `LoginPage` instead of `SecurePage`:

```js
    await expect(LoginPage.flashAlert).toBeNotExisting();
    await expect(LoginPage.flashAlert).toHaveTextContaining(
        'Your password is invalid!');
```

9). Run the tests using

```sh
npm run wdio
```

The tests should now pass.

## Add a logout test

1). In the `test/pageobjects/` folder modify the `secure.page.js` and add the following:

```js
    get btnLogout() {
        return $('a.button');
    }
    async logout() {
        await this.btnLogout.click();
    }
```

We now have a method in our page object that will allow us to click the logout button.

2). Add another test to confirm that after login, you can logout. Update the `login.spec.js` file with the following test:

```js
    it('should logout', async () => {
        await LoginPage.open();

        await LoginPage.login('tomsmith', 'SuperSecretPassword!');
        await expect(browser).toHaveUrl('https://the-internet.herokuapp.com/secure');
        
        await SecurePage.logout();
        await expect(browser).toHaveUrl('https://the-internet.herokuapp.com/login');
    });
```

- Note we are using a new matcher here. More can be found at [](https://webdriver.io/docs/api/expect-webdriverio)

3). Run your tests and they should all pass.

```sh
npm run wdio
```

---

## Skipping Tests

The most common way to skip tests is to comment them out in the code

```sh
// anything after the slashes does not execute
```

1. Comment out one of the tests and run the tests to confirm that only two of the tests run.

2. Next, uncomment the tests and ensure that they are all running.

3. Now try placing an `x` before the `it` and run your tests. It should skip the tests with `xit`.

## Nesting groups of tests

1). In the `login.spec.js` file wrap the test blocks of code with another describe block

```js
describe('My Login application', () => {
    describe('can login and log out', () => {
        it('should login with valid credentials', async () => {
            await LoginPage.open();

            await LoginPage.login('tomsmith', 'SuperSecretPassword!');
            await expect(SecurePage.flashAlert).toBeExisting();
            await expect(SecurePage.flashAlert).toHaveTextContaining(
                'You logged into a secure area!');
            await SecurePage.logout();
        });
        it('should fail to login with invalid credentials', async () => {
            await LoginPage.open();

            await LoginPage.login('tomsmith', 'wrong');
            await expect(LoginPage.flashAlert).toBeExisting();
            await expect(LoginPage.flashAlert).toHaveTextContaining(
                'Your password is invalid');
        });
        it('should logout', async () => {
            await LoginPage.open();

            await LoginPage.login('tomsmith', 'SuperSecretPassword!');
            await expect(browser).toHaveUrl('https://the-internet.herokuapp.com/secure');
            
            await SecurePage.logout();
            await expect(browser).toHaveUrl('https://the-internet.herokuapp.com/login');
        });
    });
});
```

2). Run your tests

```sh
npm run wdio
```

you should now see

`<img src="./../images/terminal-new-describe.png" alt="my-login-application" />`

---

## Prepare docker-compose and Run selenium

Create a new file called docker-compose.yaml by clicking the New File icon in the Side Bar section of the code editor.

`<img src="./../images/icon-new-file.png" />`

Paste the following:

```yml
# To execute this docker-compose yml file use `docker-compose -f docker-compose-v3.yml up`
# Add the `-d` flag at the end for detached execution
# To stop the execution, hit Ctrl+C, and then `docker-compose -f docker-compose-v3.yml down`
version: "3"
services:
  chrome:
    image: selenium/node-chrome:4.1.1-20211217
    shm_size: 2gb
    depends_on:
      - selenium-hub
    environment:
      - SE_EVENT_BUS_HOST=selenium-hub
      - SE_EVENT_BUS_PUBLISH_PORT=4442
      - SE_EVENT_BUS_SUBSCRIBE_PORT=4443

  edge:
    image: selenium/node-edge:4.1.1-20211217
    shm_size: 2gb
    depends_on:
      - selenium-hub
    environment:
      - SE_EVENT_BUS_HOST=selenium-hub
      - SE_EVENT_BUS_PUBLISH_PORT=4442
      - SE_EVENT_BUS_SUBSCRIBE_PORT=4443

  firefox:
    image: selenium/node-firefox:4.1.1-20211217
    shm_size: 2gb
    depends_on:
      - selenium-hub
    environment:
      - SE_EVENT_BUS_HOST=selenium-hub
      - SE_EVENT_BUS_PUBLISH_PORT=4442
      - SE_EVENT_BUS_SUBSCRIBE_PORT=4443

  selenium-hub:
    image: selenium/hub:4.1.1-20211217
    container_name: selenium-hub
    ports:
      - "4442:4442"
      - "4443:4443"
      - "4444:4444"
```

## Using Selenium Grid

1). Run the grid using:

```sh
docker-compose up -d
```

2). You can see the status screen at `http://localhost:4444`

3). Modify the file `wdio.conf.js` and remove on line 113.

```yml
services: ['chromedriver']
```

should become:

```yml
services: []
```

4). Now you should be able to run the tests on a selenium grid, instead of using your local browser. Start the tests using:

```sh
npm run wdio
```

5). Then go to `http://localhost:4444` and watch as the queue will show that the tests are running. You will also see output in the console.

6). Modify the file `wdio.conf.js` so that the `cababilites` object looks like the following.

```yml
capabilities: [
    {
        maxInstances: 5,
        browserName: 'chrome',
        acceptInsecureCerts: true
    },
    {
        maxInstances: 5,
        browserName: 'MicrosoftEdge',
        acceptInsecureCerts: true
    },
    {
        maxInstances: 5,
        browserName: 'firefox',
        acceptInsecureCerts: true
    }

],
```

7). Now  when you run the test, it will execute on multiple browsers concurrently. Start the tests using:

```sh
npm run wdio
```

8). Then go to `http://localhost:4444` and watch as the queue will show that the tests are running. You will also see the test executing in multiple browsers.

## Bonus

- Try nesting a describe block inside another describe block, how does that change the test suite?

- Try creating a new test for the `https://the-internet.herokuapp.com/key_presses` page, see if you can press a key and then confirm it is displayed in the UI (remember to use a page object).
