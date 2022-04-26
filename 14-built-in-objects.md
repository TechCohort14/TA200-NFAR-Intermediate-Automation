# Exercise 14: Built in Objects

Now that we've had some  practice with Objects, let's take a look at some of Javascript's built in Objects.

## What are Javascript's built-in Objects?

JavaScript provides several built-in objects that are available to use out  the box. Each object has it's own properties, and methods associated with it. We will take a look at the Math objects.

### Math Object

We can access the Math object simply by calling `Math`.

```js
console.log(Math);
```

Upon logging the Math object you can see a list of all the properties and methods that are attached to the Math object that we can use. Here

One of the properties attached to the Math object is `PI`. Pi - popularly shortened to 3.14159 - is the circumference - that is, the outside perimeter - of a circle with diameter 1. For circles with a diameter greater or less than 1, we typically use the formula 2 × pi × r (The radius being exactly half the diameter, or the distance between the center of the circle and the perimeter).

Pi is irrational - it goes on forever and ever - and can never be expressed completely as a number, fraction, or decimal. Your browser can’t store an infinite number, so JavaScript shortens PI to 3.141592653589793, which is more than accurate enough for most purposes.

While it’s most common application is finding the circumference and area of circles, pi is also used in probability, statistics, engineering and science: as a universal constant, it shows up everywhere.

```js
console.log(Math.PI);
```

There are other properties attached to the Math object as well, like: `E`. e is also known as Euler’s number, it is also an irrational number. JavaScript approximates it as 2.718281828459045

Alongside the built-in constants, there are also built-in methods. in the Math object. One of these methods is called `round`.

Let take a look at how it works.

```js
let num =  5.7;
```

Now lets round it.

```js
console.log(Math.round(num));
```

Let's see what happens if the value of `num` is 5.2;

```js
let num = 5.2;
console.log(Math.round(num));
```

Try using the following methods to see how they act.

Try using the `.floor` method.
Try using the `.ceil` method.
Try using the `.trunc` method.
Try using the `.random` method

Exercises

1). Write a function to generate a random number.
Function `genRandom()` return a generated random integer number between the provided start and end range.

Start 80 and end 90.
Start 1 and end 10.

2).Write a function to find the area of a Circle

Function `areaOfACircle()` returns the area of the circle provided the radius as an argument for the function call.

Radius = 30
Radius = 20
Radius = 10

Complete the [Object Oriented Programming](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/#object-oriented-programming) section of the Free Code Camp Curriculum.
