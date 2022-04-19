# Exercise 12: Objects

Similaly to Arrays an object in JavaScript can hold several pieces of information. An object is a collection of unordered key-value pairs. The key-value pairs are called a properies.

The key of a property can only be a string, while the value of a property can be any value, for example, a string, a number, an array, and even a function.

JavaScript provides you with many ways to create an object. The most commonly used one is to use the object literal notation.

The following example creates an empty object using the object literal notation:

```js
let emptyObject = {};
```

In order to create an object with properties, you  simply use the key:value within the curly braces. For example, the following  code creates a new president object:

```js
let president = {
    firstName: 'George',
    lastName: 'Washington'
};
```

The `president` object has two properties `firstName` and `lastName` with the corresponding values `'George'` and `'Washington'`.

You use  a comma `(,)` to separate properties in an object, like the above example.

## How to access a property

In order to access a property of an object, you can use one of two notations: the dot notation or array-like notation.

1). Dot notation `(.)`

The following example illustrates how to use the dot notation to access a property of an object:

```js
nameOfObject.propertyName
```

For example, to access the `firstName` property of the `president` object, you use the following expression:

```js
president.firstName
```

This example creates a `president` object and shows the first name and last name to the console:

```js
let president = {
    firstName: 'John',
    lastName: 'Adamns'
};

console.log(person.firstName);
console.log(person.lastName);
```

2). Bracket- notation / Array-like notation ([])

The following illustrates how to access the value of an object’s property via the array-like notation:

```js
objectName['propertyName']
```

For example:

```js
let president = {
    firstName: 'George',
    lastName: 'Washinhgton'
};

console.log(president['firstName']);
console.log(president['lastName']);
```

When a property name contains spaces, you need to place it inside quotes. For example, the following `address` object has the `'building number'` as a property:

```js
let address = {
    'building number': 3960,
    street: 'East 51st street',
    state: 'CA',
    country: 'USA'
};
```

To access the `'building number'` property, you need to use the array-like notation:

```js
address['building number'];
```

If you use the dot notation, you’ll get an error:

```js
address.'building number';
```

Error:

```shell
SyntaxError: Unexpected string
```

*Note: it is not a good practice to use spaces in the property names of an object.*

Trying to read from a property that does not exist will result in an `undefined`. For example:

```js
console.log(address.district);
```

Output

```shell
undefined
```

## Modifying the value of a property of an object

To change the value of a property, you use the assignment operator (`=`). For example:

```js
let president = {
    firstName: 'George',
    lastName: 'Washington'
};

president.lastName = 'Bush';

console.log(president);
```

Output

```shell
{ firstName: 'George', lastName: 'Bush' }
```

In this example, we changed the value of the `lastName` property of the `president` object from `'Washington'` to `'Bush'`.

## How to add a new property to an object

Objects in other programming languages such as Java and C#, are more strict and don't allow you to add properties to the object after object creation. However in JavaScript you can do just that.

The following statement adds the `age` property to the `president` object and assigns `57`to it:

```shell
president.age = 25;
```

## Deleting a property

To delete a property of an object, you use the `delete` operator:

```js
delete objectName.propertyName;
```

The following example removes the `age` property from the `president` object:

```js
delete president.age;
```

If you attempt to reaccess the age property, you’ll get an `undefined` value.

## Checking if a property exists

To check if a property exists in an object, you use the `in` operator:

```js
propertyName in objectName
```

The `in` operator returns `true` if the `propertyName` exists in the `objectName`.

The following example creates an `student` object and uses the `in` operator to check if the `age` and `studentId` properties exist in the object:

```js
let student = {
    firstName: 'Joe',
    lastName: 'Doe',
    studentId: 1
};

console.log('age' in student);
console.log('studentId' in student);
```

Output:

```shell
false
true
```

### Summary

- An object is a collection of key-value pairs.
- You can use the dot notation (`.`) or array-like notation (`[]`) to access a property of an object.
- The `delete` operator removes a property from an object.
- The `in` operator check if a property exists in an object.

### Practice

For each of the exercises below, assume you are starting with the following programming object.

```js

let learningToCode = {
    languages: ["JavaScript", "C#", "Java"],
    isDifficult: true,
    difficulty: 8,
    isRewarding: true,
    humor: "https://www.reddit.com/r/ProgrammerHumor/"
}

```

### Setup

1). Create a new folder;

```sh
mkdir learningObjects
```

2). Change directory into the new folder:

```sh
cd learningObjects
```

3). Create a new file called main.js

```sh
touch main.js
```

1. Write the command to add the language "Go" to the end of the languages array.
2. Change the difficulty to the value of 7.
3. Using the delete keyword, write the command to remove the humor key from the learningToCode object.
4. Write the command to add a new key called isFun and a value of true to the learningToCode object.
5. Using a loop, iterate through the languages array and console.log all of the languages.
6. Using a loop, console.log all of the keys in the learningToCode object.
7. Using a loop, console.log all of the values in the learningToCode object.

We've covered a lot on objects. Continue working on the [Free Code Camp](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/) training on Basic Javascript to gain a further understanding of topics that we've covered.
