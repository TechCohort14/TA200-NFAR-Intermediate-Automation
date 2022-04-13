# Exercise 11: Multi-Dimensional Arrays

In the previous lesson we learned anout the different characteristics of an array. We also practiced using methods to interact with our arrays. One characteristic of an array is that it can store multiple values with different types. Arrays have the ability to store, numbers, string, boolean, and even arrays. An array within an array is called a multi-dimensional array. A better way of saying this is, a multi-dimensional array is an array where the values inside of the array are also arrays. The inner arrays can store many other values. These values can include strings, numbers, or even more arrays.

The example below demonstrates an array called `listOf` has arrays as values. The inner arrays contain words that are synonyms of each other. Notice each inner array has an index position.

```js
let listOf =
```

     | 0        |      1        |  2    |
     |:--------:|:-------------:|:-----:|
   0 | apples   |  bananas      | plums |
      ----------------------------------
   1 | Ford     |  Toyota       | Honda |
      ----------------------------------
   2 | Red      | Yellow        | Blue  |
      ----------------------------------
   3 | North    | South         | East  |

## Two Dimensional Arrays

The simplest form of a multi-dimensional array is a two dimensional array. A two dimensional array is like a spreadsheet with rows and columns. To access items in a two dimensional array, use square bracket notation and two indexes array[0][0]. The first index is for the outer array, or the "row", and second index is for the inner array, or the "column".

**Note**
*The row and column analogy is used to help visualize a two dimensional array, however it's not a perfect analogy. There are no specific JavaScript language rules forcing the inner arrays to all have the same length. The inner arrays are separate arrays that can be of different length.*

Use a two dimensional array to contain three different lists of space shuttle crews.

```js
let shuttleCrews = [
   ['Robert Gibson', 'Mark Lee', 'Mae Jemison'],
   ['Kent Rominger', 'Ellen Ochoa', 'Bernard Harris'],
   ['Eilen Collins', 'Winston Scott',  'Catherin Coleman']
];

console.log(shuttleCrews[0][2]);
console.log(shuttleCrews[1][1]);
console.log(shuttleCrews[2][1]);
```

Console Output

```sh
Mae Jemison
Ellen Ochoa
Winston Scott

```

## Multi-Dimensions and Array Methods

In a multi-dimensional array, both the inner and outer arrays can be altered with array methods. However, bracket notation must be used correctly.

To apply a method to the outer array, the syntax is:

```js
multiArrayName.method();
```

To apply a method to one of the inner arrays, the syntax is:

```js
multiArrayName[indexOfInnerArray].method();
```

Use array methods to add an additional crew array and alter existing arrays.

```js
let shuttleCrews = [
   ['Robert Gibson', 'Mark Lee', 'Mae Jemison'],
   ['Kent Rominger', 'Ellen Ochoa', 'Bernard Harris'],
   ['Eilen Collins', 'Winston Scott',  'Catherin Coleman']
];

let newCrew = ['Mark Polansky', 'Robert Curbeam', 'Joan Higginbotham'];

// Add a new crew array to the end of shuttleCrews
shuttleCrews.push(newCrew);
console.log(shuttleCrews[3][2]);

// Reverse the order of the crew at index 1
shuttleCrews[1].reverse();
console.log(shuttleCrews[1]);
```

```terminal
Joan Higginbotham
[ 'Bernard Harris', 'Ellen Ochoa', 'Kent Rominger' ]
```

## Beyond Two Dimensional Arrays

Generally, there is no limit to how many dimensions you can have when creating arrays. However it is rare that you will use more than two dimensions. Later on in the class we will learn about more collection types that can handle complex problems beyond the scope of two dimensional arrays.

## Check Your Understanding

What are the two dimensional indexes for "Jones"?

```js
let school = [
   ["science", "computer", "art"],
   ["Jones", "Willoughby", "Rhodes"]
];
```

How would you add "dance" to the array at school[0]?

How would you add "Holmes" to the array at school[1]?