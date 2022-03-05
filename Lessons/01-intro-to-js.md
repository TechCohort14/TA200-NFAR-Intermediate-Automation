# EXERCISE 01: Introduction to Javascript

In this lesson we will discuss what JavaScript's is. We will also go over soeme basic grammar, variable declarations, data types and literals.

---

## What is Javascrip?

**What is Javascript?**

JavaScript is a cross-platform, object-oriented scripting language used to add functionality and interactivity to webpages. For example, having clickable buttons, popup menus, etc. There are also more advanced server side versions of JavaScript like Node.js, which allow you to add more functionality to a website, like realtime collaboration between multiple computers. Inside a host environment such as a web browser, JavaScript can be connected to the objects of its environment to provide programmatic control over them.

JavaScript contains a library of objects, such as `Date`, `Math`, and `Array`, and a core set of language elements such as operators, control structures, and statements. Core JavaScript can be extended for a variety of purposes by supplementing it with additional objects; for example:

Client-side JavaScript extends Javascript's core language by providing objects to control a browser and its Document Object Model (DOM). For example, client-side extensions allow an application to place elements on an HTML form and respond to user events such as mouse clicks, form input, and page navigation.

Server-side JavaScript extends Javascript's core language by providing objects relevant to running JavaScript on a server. For example, server-side extensions allow an application to communicate with a database, provide continuity of information from one invocation to another of the application, or perform file manipulations on a server.
This means that in the browser, JavaScript can change the way the webpage (DOM) looks. And, likewise, Node.js JavaScript on the server can respond to custom requests from code written in the browser.

---

## Basics

Javascript is case-sensitive, so the variables `fun` and `Fun` are not equal. Instructions in Javascript are called statements and are seperated by semicolon`(;)`.
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

A JavaScript identifier must start with a letter, underscore (_), or dollar sign ($). Subsequent characters can also be digits (0–9).

Because JavaScript is case sensitive, letters include the characters "A" through "Z" (uppercase) as well as "a" through "z" (lowercase).

You can use most of ISO 8859-1 or Unicode letters such as å and ü in identifiers. (For more details, see this blog post.) You can also use the Unicode escape sequences as characters in identifiers.









## Setup a project

1. Create a new folder;

```
$ mkdir myFirstReport
```

2. Change directory into the new folder:

```
$ cd myFirstReport
```

4. Install web driver.io (don't forget the space and period they are required)

```
$ npm init wdio .
```

---

## Install report dependencies

1. Install node static which will allow us to view local html pages in our browser.

```
$ sudo npm i -g node-static
```

2. Install the Nice HTML reporter

```
$ npm i wdio-html-nice-reporter node-static
```

---

## Update the configuration

1. Open the `wdio.conf.js` file in your code editor.

2. Make an update to the configuration and around line 135 where it says:

```
reporters: ['spec']
```

Copy and paste the following new configuration (don't forget the comma at the end).

```
reporters: ['spec',
        ["html-nice", {
            outputDir: './reports/html-reports/',
            filename: 'report.html',
            reportTitle: 'Test Report Title',
            linkScreenshots: true,
            //to show the report in a browser when done
            showInBrowser: true,
            collapseTests: false,
            //to turn on screenshots after every test
            useOnAfterCommandForScreenshot: false,

        }
        ]
    ],
```


## Running your first test to generate a report

You can start the tests using:

```
$ npm run wdio
```

You should see a browser open, run the tests in a browser, and then the browser will close.

---

## Review the report

1. In your terminal change directories to your reports folder

type

```
$ cd reports/html-reports/suite-0-0/0-0
```

or change directories one at a time

```
$ cd reports
$ cd html-reports
$ cd suite-0-0
$ cd 0-0
```

Remember if you get lost you can always list the directories and files using the `ls` command.

```
$ ls
```

2. Serve up the `html` file (remember to include the space and period)

```
$ static .
```

3. View the file in your Chrome browser go to your browser and view the report at the following URL http://127.0.0.1:8080/report.html

4. When you are done reviewing the reports you will need to use `Command + C` to exit out of the server.

---

## Prepare docker-compose

Create a new file called docker-compose.yaml by clicking the New File icon in the Side Bar section of the code editor.

<img src="./../images/icon-new-file.png" alt="new-file-image" />




Paste the following:

```

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

1. Run the grid using:

```
$ docker-compose up -d
```

2. You can see the status screen at `http://localhost:4444`

3. Modify the file `wdio.conf.js` and remove on line 113.

```
services: ['chromedriver']
```
should become:

```
services: []
```

4. Now you should be able to run the tests on a selenium grid, instead of using your local browser. Start the tests using:

```
$ npm run wdio
```

5. Then go to `http://localhost:4444` and watch as the queue will show that the tests are running. You will also see output in the console.

6. Modify the file `wdio.conf.js` so that the `cababilites` object looks like the following.

```
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
7. Now  when you run the test, it will execute on multiple browsers concurrently. Start the tests using:

```
$ npm run wdio
```

8. Then go to `http://localhost:4444` and watch as the queue will show that the tests are running. You will also see the test executing in multiple browsers.
Bonus:

* Create another type of report. Pick another reporter and generate a new report.
