# Exercise 08: More on loops

Let's take a look at a few examples.

We use a `for` loop when we know how many time we want to run a loop.

```javascript
for (let i = 0; i <= 10; i++) {
console.log(i);
}

```

A `while` loop is used to evaluate whether an expression is true.

```javascript
let isRequired = true;

while(isRequired) {
    console.log(isRequired)
    isRequired = false;
}

```

```javascript
for (let n = 1; n <= 10; n++){
    if(n % 2 == 0){ // we used the == to compare the values. The single = is used to assign a value
        console.log(n)
    }
}
```

How would we change the code above to log common multiples of 2 and 5?

Try changing the condition to say `n <= 100`. What will the output be?

How would we change the code to log either multiples of 2 or 5?

----------------------

## Practice exercises

Your objective is to construct a loop to solve each scenario.

You are going on a trip and need fuel up. Your vehicle has a 12 gallon tank. Write a loop that logs a message when the tank is full.

```javascript
var fuelLevel = 0;

while(fuelLevel < 12) {
    fuelLevel += 1;
}
console.log(fuelLevel + " gallons is enough to begin your trip");
```

Create a loop that will log a warning message when you down to a quater tank of gas. Let's assume that we start with a full tank at 12 gallons.

Create a loop that will tell you how many gallons are required for your trip. Let's assume that your vehicle gets 22 miles per gallon, and the trip is 100 miles.

Create 2 other scenarios and creat a loop toi solve them.
