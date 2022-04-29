# Exercise 13: More On Objects

In the previous lesson we were introduced to objects. Let's recap what we learned and add some more context to gain a better understanding.

We mentioned that:

- An object is a collection of key-value pairs.
- Each key-value pair is called a property.
- You can use the dot notation (`.`) or array-like notation (`[]`) (also called object literal) to access a property of an object.
- The `delete` operator removes a property from an object.
- The `in` operator check if a property exists in an object.

A great way to think of objects is to compare them to objects in real life. The following example shows the coorlation between an object in the real world and objects in JavaScript.

![js-object-example](assets/js_object2.png)

```js
let car = {
    'name':'Mitsubishi',
    'model':'Super Lancer',
    'weight':1300,
    'year': 1996,
    'color':'Grey',
    'start': function () {
        console.log("Vroom!")
    },
    'honk': function () {
        console.log("Beep Beep")
    }
}
```

As you can see, objects in the real world and objects in JavaScript are very similar. They both have properties. They also have things they can do, which in JavaScript are called methods (which are also just functions associated with an object).

The method defines an action that can be performed by the object. Using the example above, if we were to call `car.honk()`, it would `console.log('Beep Beep')`

## JSON: JavaScript Object Notations

 JSON is a data format similar to JavaScript objects. It is a plain text format, and can be saved in a plain text file (usually with the .json file extension).

JSON and JavaScript objects are also very easily interchangeable. For that reason, JSON is the most commonly used format for exchanging data between the server and the client in web applications. The principal difference between JSON and JavaScript objects is as follows:

A JavaScript object is a data type in the JavaScript environment. Outside of the JavaScript environment a JavaScript object does not make sense. A JSON instance is a plain text string, formatted in a certain way according to the JSON standard. Thus a JSON string is not limited to the JavaScript environment. It can exist in other programming languages, or simply stored inside a plain text file or a database.
A JavaScript object can be created using an expression such as the following one:

```js
let myObj = {
    x: 8,
    y: 9};
```

While the corresponding JSON string can be defined, and stored in a variable, like the following:

```js
let myJson = '{"x": 8, "y": 9}';
```

A major difference between how the two variables are defined is that in a JSON string the property names are enclosed in quotes: `"x"` and `"y"`. The JSON standard requires double quotes (`"`), so we need to enclose the entire string with single quotes (`'`).

In order to make a JSON string useful within the JavaScript environment, the JSON string can be parsed. Parsing the string will return an object. The parsing process, JSON → object, is done with the JSON.parse function. The JSON.parse function is used to convert a JSON string to a JavaScript object:

```js
JSON.parse(myJson);  // Will return an object
```

## Functions

A function is a block of code we use to perform a particular task. Defining functions allows you to reuse that function over and over again, in separate parts of your JavaScript file. All you would need to do is call the function.

### You define a function with

- The function keyword
- A function name of our choice, such as `myFunc` or `login`
- Parameter names separated by commas, inside parentheses (`( and )`), such as (`x, y`)
- The code to be executed by the function, curly brackets (`{ and }`), such as `{return x * y;}`
  
  The function block may contain more than one expression. One or more of those can contain the `return` keyword, followed by a value the function returns when executed. When a `return` expression is reached the function stops, and the value after `return` is returned by the function. In case there is no `return` expression in the function code, the function will  return `undefined`.

For example, the following expression defines a function named add. The add function has two parameters, x and y. The function returns the result of adding x and y.

```js
// Defining a function
function add(x, y) {
    return x + y;
}
```

Once the function is defined, you can execute it with specific arguments. This is known as a function call. For example, the following expression is a function call of the add function, returning 9:

```js
// Calling a function
add(4, 5); 
```

Remember, there is a difference between parameters and arguments. Parameters are the names listed in the function definition. You can think of them as placeholders. Arguments are the real values passed to the function when it is called. In the example above, the parameters of the add function are x and y. The arguments in the function call of add were 4 and 5.

It is not required for a function to have parameters, and it does not necessarily need to return any value. For example, here is a function that has no parameters and does not return a value

```js
function greeting() {
  console.log("Hey!");
}
```

The code in the greeting function uses the console.log function. The console.log function prints text into the console.

```js
greeting();  // Logs "Hey!" in the console
```

The console.log function is very helpful when experimenting with JavaScript code, and we will use it often. For example, when running a long script we may wish the current value of a variable to be printed out, to monitor its change through our program.

To keep the returned value of a function for future use, we use assignment

```js
var sum;
sum = add(4, 5);
```

Now let's try some practice exercises.

### Practice Exercise 1

1). Create a function that checks two numbers and returns `true` if the sum of the numbers is equal to 1000, or if the value of either number is equal to 1000.

2). Create a function that returns a list of extension when given an array of file names. Use the following file names. `'index.html'`, `'main.js'`, `'styles.css'`.

3). Write a function to convert Celsius to Fahrenheit
Function `calFahrenheit()` returns the converted Celsius value to Fahrenheit value based on the formula `(Celsius × 9/5) + 32 = Fahrenheit`

4). Write a function named calculateDogAge that:

- takes 1 argument: your puppy's age.
- calculates your dog's age based on the conversion rate of 1 human year to 7 dog years.
- outputs the result to the screen like so: "Your doggie is NN years old in dog years!"
- Call the function three times with different sets of values.

5). The Lifetime Supply Calculator
Ever wonder how much a "lifetime supply" of your favorite snack is? Wonder no more!

Write a function named calculateSupply that:

- takes 2 arguments: age, amount per day.
- calculates the amount consumed for rest of the life (based on a constant max age).
- outputs the result to the screen like so: "You will need NN to last you until the ripe old age of X"
- Call that function three times, passing in different values each time.
