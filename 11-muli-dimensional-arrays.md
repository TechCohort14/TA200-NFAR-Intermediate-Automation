# Exercise 11: Multi-Dimensional Arrays

In the previous lesson we learned anout the different characteristics of an array. We also practiced using methods to interact with our arrays. One characteristic of an array is that it can store multiple values with different types. Arrays have the ability to store, numbers, string, boolean, and even arrays. An array within an array is called a multi-dimensional array. A better way of saying this is, a multi-dimensional array is an array where the values inside of the array are also arrays. The inner arrays can store many other values. These values can include strings, numbers, or even more arrays.

The example below demonstrates an array called `listOf` that has arrays as values. The inner arrays contain words that are related in some way, like fruits, cars, colors, etc. Notice each inner array has an index position.

```js
let listOf =
```

```js

     | 0        |      1        |  2    |
     |:--------:|:-------------:|:-----:|
   0 | apples   | bananas       | plums |
   1 | Ford     | Toyota        | Honda |
   2 | Red      | Yellow        | Blue  |
   3 | North    | South         | East  |
```

## Two Dimensional Arrays

One type of multi-dimensional array is the Two Dimensional array. This is the simplest form of a multi-dimensional. A two dimensional array is like a spreadsheet with rows and columns. To access items in a two dimensional array, use square bracket notation and two indexes array`[0][0]`. The first index is for the outer array, or the "row", and second index is for the inner array, or the "column".

**Note**
*The row and column analogy is used to help visualize a two dimensional array, however it's not a perfect analogy. There are no specific JavaScript language rules forcing the inner arrays to all have the same length. The inner arrays are separate arrays that can be of different length.*

This example uses a two dimensional array to contain three different lists of super heroes.

```js
let superHeroes = [
   ['Superman', 'Batman', 'Spiderman'],
   ['Wolverine', 'Storm', 'Cyclops'],
   ['Goku', 'Vegeta',  'Gohan']
];

console.log(superHeroes[0][2]);
console.log(superHeroes[1][1]);
console.log(superHeroes[2][1]);
```

Output

Spiderman
Storm
Vegeta

## Multi-Dimensions and Array Methods

Both the inner and outer arrays in a multi-dimensional array can be altered with array methods. However, it is important to use bracket notation correctly.

The example below shows how to apply a method to the outer array:

```js
myMultiArray.method();
```

To apply a method to one of the inner arrays, the syntax is:

```js
myMultiArray[indexOfInnerArray].method();
```

Use array methods to add an additional superhero array and alter existing arrays.

```js
let superHeroes = [
 ['Superman', 'Batman', 'Spiderman'],
   ['Wolverine', 'Storm', 'Cyclops'],
   ['Goku', 'Vegeta',  'Gohan']
];

let newHeroes = ['Invisible Woman', 'Thing', 'Human Torch'];

// Try this

// Add a new newHeroes array to the end of superHeroes
superHeroes.push(newHeroes);
console.log(superHeroes[3][2]);

// Reverse the order of the superHeroes at index 1
superHeroes[1].reverse();
console.log(superHeroes[1]);
```

## Beyond Two Dimensional Arrays

There are generally no limit to how many dimensions you can have when creating arrays. However it is rare that you will use more than two dimensions.

## Check Your Understanding

What are the two dimensional indexes for "Jones"?

```js
let friends = [
   ["Adam", "Bob", "Chuck"],
   ["Dennis", "Earl", "Frank"]
];
```

How would you add "Jeff" to the array at friends[0]?

How would you add "Holmes" to the array at friends[1]?
