# Exercise 10: More on Arrays

In the previous lesson we discused arrays. We also took a look at some of the methods that we can use to interact with, and modify arrays. In this lesson, we will practice using those array methods to gain a further understanding.

It's time to stretch those array methods muscles. You will be given an example and a set of instructions to complete using a different array method. You will log your output to the console using `console.log()`.

## Setup

1). Create a new directory called arrayExercises and cd into that directory

```sh
mkdir arrayExercises
```

2). Create a new file called main.js

```sh
touch main.js
```

3). Open in VS code

```sh
code .
```

## Exercise

Create an array called arrExample with the following entry: 434.43. Use the push method to add the following elements to the array.
Add items a & b one at a time, then use a single push to add the items in part c.
Print the array after each step to confirm the changes.

a. 9

b. "hello world"

c. true, -3.9, "152"

---

The `push`, `pop`, `shift` and `unshift` array methods are used to add/remove elements from the beginning/end of an array. Bracket notation can be used to modify any element within an array. Create an array called supplyKit which contains the following elements`['rain coat', 'matches', 'blanket', 'water', 'meal packs', 'knife', 'first aid']`, write statements to do the following:

a. Use bracket notation to replace `'matches'` in the array with `'lighter'`. Log the array to confirm the change.

b. Remove the last element from the array. Log the element removed and the updated array.

c. Remove the first element from the array. Log the element removed and the updated array.

d. Unlike pop and shift, push and unshift require arguments inside the ``()``. Add the elements `'twine'` and `'compass'` to the array - `'twine'` at the start and `'compass'` at the end. Log the updated array to confirm the changes.

e. Use a template literal to log the final array and its length.

Which array methods ADD elements, and where are the new entries placed? Which methods REMOVE elements, and where do the entries come from? Which methods require entries inside the ``()``?

---

The splice method can be used to either add or remove items from an array. It can also accomplish both tasks at the same time. Checkout the [splice](https://www.w3schools.com/jsref/jsref_splice.asp) to get familiar with the syntax. Use splice to make the following changes to the final supplyKit array from exercise 2. Be sure to log the array after each step to confirm your updates.

a. Insert the string `'rope'` at index 3 without replacing any other entries.

b. Remove `'knife'` from the array. (Hint: `indexOf` is helpful to avoid manually counting an index).

c. Replace the elements at indexes `2` - `4` with the items `'water bottle'`, ``'socks'``, and `'jacket'`.

Now let's look deeper into details about array methods.

---

Some methods---like `splice` and `push`---alter the original array, while others do not. Use the arrays

```js
desk1 ['pencils', 'notebook', 3.14, true, 6.022e23]
```

and

```js
desk2 ['pen', 'laptop', 'camera', 42, 'phone']
```

to explore the following methods: [concat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/concat), [slice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice), [reverse](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reverse), [sort](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort). Click each method to see the syntax and how each method works.

a. Log the result of using `concat` on the two arrays. Does `concat` alter the original arrays? Verify this by printing desk1 after using the method.

b. Log a slice of two elements from each array. Does slice alter the original arrays?

c. `reverse` the first array, and sort the second. What is the difference between these two methods? Do the methods alter the original arrays?

---

The `split` method converts a string into an array, while the `join` method does the opposite.

a. Given the string `message = 'In the forest, no one can hear you code.'`, see what happens when you log message.split() vs. message.split('e') vs. message.split(' ') vs. message.split(''). What is the purpose of the parameter inside the ()?
Give it a try.

b. Given the array myArray = ['A', 'c', 'c', 7], see what happens when you log myArray.join() vs. myArray.join('a') vs. myArr.join(' ') vs. myArray.join(''). What is the purpose of the parameter inside the ()?

c. Do split or join change the original string/array?

d. Alphabetize these: `"coffee,tea,juice,water,wine"`, and then combine them into a new string. Try it!

---

Arrays can hold different data types, even other arrays! A multi-dimensional array is one with entries that are themselves arrays.

a. Define and initialize the following arrays, which hold the name, chemical symbol and mass for different elements:

1. elem1 = ['hydrogen', 'H', 1.008]
2. elem2 = ['helium', 'He', 4.003]
3. elem3 = ['iron', 'Fe', 55.85]

b. Define the array table, and use push(arrayName) to add each of the element arrays to it. Log table to see its structure.

c. Use bracket notation to examine the difference between printing `table[1]` and `table[1][1]`. Don't just nod your head! I want to HEAR you describe this difference. Go ahead, talk to your screen.

d. Using bracket notation and the table array, print the mass of elem1, the name for elem 2 and the symbol for elem26.

e. table is an example of a 2-dimensional array. The first "level" contains the element arrays, and the second level holds the name/symbol/mass values. Experiment! Create a 3-dimensional array and print out one entry from each level in the array.

We've covered a lot on arrays. Continue working on the [Free Code Camp](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/) training on Basic Javascript to gain a further understanding of topics that we've covered.
