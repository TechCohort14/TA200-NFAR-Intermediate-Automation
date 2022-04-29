# Exercise 09: Arrays

In this lesson, we will take a look Arrays in Javascript.

---

## What are Arrays?

An array is a variable that can hold more than one value. Arrays are ordered lists of values. Each value is called an element, and is specified by an index.

```js
const students = ["Daniel", "David", "Juan", "Girish", "Gage"];
```

If we stored the names of each student to an individual variable, it would look like the following.

```js
let student1 = "Daniel";
let student2 = "David";
let student3 = "Juan";
let student4 = "Girish";
let student5 = "Gage";
```

![arrays](./assets/array.png)

### Charateristics of an array

An array can hold values with different data types. For example, you can have an array that stores elements with the data types number, string, and boolean.

```js
const myArray = [1, "two", true, 4, "false"]
```

The size of an array is dynamic. You do not need to specify the size of the array upfront.

### Creating an array

```js
let grades = new Array();
```

 This example uses the `Array` constructor. The grade array is currently empty.

---

```js
let grades = Array(5);
```

You can also include the size of the array, if you know how many elements the array will hold.

---

```js
let grades = new Array(90,100,80,70,75);
```

You can also create an array and initialize it with some elements. You simply pass the elements as a comma-separated list into the `Array()` constructor.

*When you use the `Array()` constructor to create an array and pass a number into it, you are creating an array with an initial size.*

```js
let grades = Array();
```

JavaScript also allows you to omit the `new` operator when you use the Array() constructor like in the example above.

---

While it is important to know and understand how to use the `Array()` constructor, you’ll rarely ever use it in the practice. The more popular way of creating an array is using array literal notation.

Square brackets are used to wrap a comma separated list of elements.

```js
let pets = ['cat', 'dog', 'fish', 'turtle', 'snake'];

// the pets array holds a list of string elements
```

```js
let ages = [12, 10, 6, 9];
// the ages array holds a list of number elements
```

```js
let empty = [];
// the empty array holds no elements
```

### Accessing elements in an array

The first element in an array has an index of 0. The second element has an index of 1, the third element has an index of 2 and so on. This is because Javascript arrays are zero-index based. To access an element in an array, you specify an index in the square brackets `[]`

```js
nameOfArray[index]
```

The following examples shows how to access the elements of the array:

```js
let teams = ['Pirates', 'Padres', 'Yankees'];

console.log(teams[0]); // 'Pirates'
console.log(teams[1]); // 'Padres'
console.log(teams[2]); // 'Yankees'

```

You can also change the value of an element. Assign the new value to the element by doing the following:

```js
let teams = ['Pirates', 'Padres', 'Yankees'];
teams[1] = 'Dodgers';

console.log(teams);
```

Your output will be:

```js
['Pirates', 'Dodgers', 'Yankees']
```

### Array size

Now let's imagine a situation where we were give a very long array. If we needed to find how many elements were in the array without counting each element individually, we can use the `.length` property. It looks like this:

```js
let teams = ['Pirates', 'Dodgers', 'Yankees'];
console.log(teams.length);
```

```js
// output 3
```

This is a great time to explain what properties are. In Javascript, properties are values associated with objects. For example, if we wanted to describe certain properties of a car we could mention that the car is: `red` `has 4 wheels` `has 2 door` etc.

Properties can usually be deleted, added, and changed. However, some properties are read-only.

### How to add an element top the end of an array

If we wanted to add an element to the end of an array, we would use the `.push()` method.

```js
let pets = ['cat', 'dog', 'fish', 'turtle', 'snake'];
pets.push('rabbit');

```

```js
// Output
['cat', 'dog', 'fish', 'turtle', 'snake', 'rabbit']
```

When we use the `.push()` method here, a set of instructions are executed, resulting in the `'rabbit'` element being pushed to the end of the `pets` array.

Remember, methods are a set of instructions that are associated with an object.

```javascript
/**
 * login.page.js
 * 
     * a method to encapsule automation code to interact with the page
     * e.g. to login using username and password
     */
    async login (username, password) {
        await this.inputUsername.setValue(username);
        await this.inputPassword.setValue(password);
        await this.btnSubmit.click();
    }

```

In the example above, the login method is used to execute a set of instructions which with result in the user being logged in successfully. The login method

Our example test looks like this:

```javascript
describe('My Login application', () => {
    it('should login with valid credentials', async () => {
        await LoginPage.open();

        await LoginPage.login('tomsmith', 'SuperSecretPassword!');
        await expect(SecurePage.flashAlert).toBeExisting();
        await expect(SecurePage.flashAlert).toHaveTextContaining(
            'You logged into a secure area!');
    });
```

### How to add an element to the begining of an array

The `.unshift()` method is used to add an element to the beginning of an array.

```js
let pets = ['cat', 'dog', 'fish', 'turtle', 'snake'];
pets.unshift('goat');
console.log(pets);

```

```js
// Output
['goat', 'cat', 'dog', 'fish', 'turtle', 'snake']
```

### How to remove an element from the beginning of an array

The `.shift()` method is used to remove an element to the beginning of an array.

```js
let pets = ['cat', 'dog', 'fish', 'turtle', 'snake'];
const firstElem = pets.shift();

console.log(firstElem);
```

```js
// Output
cat
```

### How to remove an element from the end of an array

The `.pop()` method is used to remove an element from the end of an array.

```js
let pets = ['cat', 'dog', 'fish', 'turtle', 'snake'];
const lastElem = pets.pop();

console.log(lastElem);
```

```js
// Output
snake
```

### How to find the index of an element in an array

```js
let pets = ['cat', 'dog', 'fish', 'turtle', 'snake'];
let elemIndex = pets.indexOf('fish');

console.log(elemIndex);
```

```js
// Output
2
```

#### To sum it all up

- An array is an order list of values. Each value is called an element and  is specified by an index.
- An array can hold values with different data types.
- Arrays are dynamic, this means that they grow or shrink as needed.
