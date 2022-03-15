# EXERCISE 03: For Loops

In this lesson, we will take a look at what JavaScript loops are. We will also go over the syntax and use cases for a For Loop.

---

## What are Loop?

Loops provide a quick and easy way to repeatedly run a command.

```javascript
for (let i = 0; i < 6; i++) {
  // Runs 6 times, with values of step 0 through 5.
  console.log('Plus 1');
}

```
In Javascript there are many different kinds of loops however, but they all do essentially the same thing, which is repeat an action a number of times. (Keep in mind that it's possible that number could be zero!)

---

## `for` Loops

A `for` loop will repeats until a condition is false. A `for` loop looks like this:

```javascript
for ([initialExpression]; [conditionExpression]; [incrementExpression]) {
  statement
  }
```
- The inital expression is executed (one time) before the execution of the code block.

- The condition expression defines the condition for executing the code block.

- The increment expression is executed (every time) after the code block has been executed.

```javascript
for (let i = 0; i < 7; i++) {
  text += "The number is " + i + "<br>";
}
```
From the example above, you can read:

The first section sets a variable before the loop starts (let i = 0).

The second section defines the condition for the loop to run (i must be less than 7).

The third section increases a value (i++) each time the code block in the loop has been executed.



When a `for` loop executes, the following occurs:

1. The initializing expression `initialExpression`, if any, is executed. This expression usually initializes one or more loop counters, but the syntax allows an expression of any degree of complexity. This expression can also declare variables.

2. The `conditionExpression`  is evaluated. If the value of `conditionExpression` is true, the loop statements execute. If the value of `condition` is false, the `for` loop terminates. (If the `condition` expression is omitted entirely, the condition is assumed to be true.)

3. The `statement` executes. To execute multiple statements, use a block statement (`{ ... }`) to group those statements.

4. If present, the update expression `incrementExpression` is executed.

5. Control returns to Step 2.

**Example**

In the example below, the function contains a `for` statement that counts the number of selected options in a scrolling list (a <select> element that allows multiple selections). The for statement declares the variable i and initializes it to 0. It checks that i is less than the number of options in the <select> element, performs the succeeding if statement, and increments i by 1 after each pass through the loop.


```javascript
<form name="selectForm">
  <p>
    <label for="musicTypes">Choose some music types, then click the button below:</label>
    <select id="musicTypes" name="musicTypes" multiple="multiple">
      <option selected="selected">Pop</option>
      <option>Dance</option>
      <option>HipHop</option>
      <option>Alternative</option>
      <option>Classical</option>
      <option>Contemporary</option>
    </select>
  </p>
  <p><input id="btn" type="button" value="How many are selected?" /></p>
</form>

<script>
function howMany(selectObject) {
  let numberSelected = 0;
  for (let i = 0; i < selectObject.options.length; i++) {
    if (selectObject.options[i].selected) {
      numberSelected++;
    }
  }
  return numberSelected;
}

let btn = document.getElementById('btn');
btn.addEventListener('click', function() {
  alert('Number of options selected: ' + howMany(document.selectForm.musicTypes));
});
</script>

```



Continue working on the [Free Code Camp](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/) training on Basic Javascript to gain a further understanding of topics that we've covered.
