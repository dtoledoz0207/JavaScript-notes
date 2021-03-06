# Conditional Statements

* [What are Conditional Statements?](#What-are-Conditional-Statements?)
* [The if keyword](#The-if-keyword)
* [If...Else Statements](#If...Else-Statements)
* [Comparison Operators](#Comparison-Operators)
* [Logical Operators](#Logical-Operators)
* [Truthy and Falsy](#Truthy-and-Falsy)
* [Truthy and Falsy Assignment](#Truthy-and-Falsy-Assignment)
* [Ternary Operator](#Ternary-Operator)
* [Else If Statement](#Else-If-Statement)
* [The switch keyword](#The-switch-keyword)


## What are Conditional Statements?
In life, we make decisions based on circumstances. Think of an everyday decision. if we are tired, we go to bed, otherwise, we wake up and start our day.

These if-else decisions can be modeled in code by creating *conditional statements*. A conditional statement checks specific condition(s) and performs a task based on the condition(s).

In this lesson we'll be covering the following concepts:

* `if`, `else if`, and `else` statements.
* comparison operators.
* logical operators.
* truthy vs falsy values.
* ternary operators.
* the `switch` statement.

## The if keyword
In programming, we can also perform a task based on a condition using an `if` statement:

```js
if (true) {
  console.log('This message will print!');
}
// Prints "This message will print!"
```

The `if` statement is composed of:

* The `if` keyword followed by a set of parentheses `()` which is followed by a *code block statement*, indicated by a set of curly braces `{}`.
* Inside the parentheses `()`, a condition is provided that evaluates to `true` or `false`.
* If the condition evaluates to `true`, the code inside the curly braces `{}` runs, or *executes*.
* If the condition evaluates to `false`, the block won't execute.

## If...Else Statements
If we wanted to add some default behavior to the `if` statement, we can add an `else` statement to run a block of code when the condition evaluates to `false`.

```js
if (false) {
  console.log('The code in this block will not run');
} else {
  console.log('But the code in this block will!');
}
// Prints "But the code in this block will!"
```

An `else` statement must be paired with an `if` statement, and together they are referred to as an `if...else` statement.

* Uses the `else` keyword following the code block of an `if` statement.
* Has a code block that is wrapped by a set of curly braces `{}`.
* The code inside the `else` statement code block will execute when the `if` statement's condition evaluates to false.

`if..else` statements allow us to automate solutions to yes-or-no questions, also known as *binany decisions*.


## Comparison Operators
When writting conditional statements, sometimes we need to use different types of operators to compare values. These operators are called *comparison operators*.

* Less than: `<`
* Greater than: `>`
* Less than or equal to: `<=`
* Greater than or equal to: `>=`
* Is equal to: `===`
* Is NOT equal to: `!==`

## Logical Operators
Working with conditionals means that we will be using booleans, `true` or `false` values. In JavaScript, there are operators that work with boolean values known as *logical operators*. We can use logical operators to add more sophisticated logic to our conditionals.

* the *and* operator (`&&`)
* the *or* operator (`||`)
* the *not* operator, otherwise known as the *bang* operator (`!`)

When using the `&&` operator, both conditions *must* evaluate to `true` for the entire condition to evaluate to `true` and execute.
Otherwise, if either condition is `false`, the `&&` condition will evaluate to `false` and the `else` block will execute.

```js
if (stopLight === 'green' && pedestrians === 0) {
  console.log('Go!');
} else {
  console.log('Stop');
}
```

When using the `||` operator, only one of the conditions must evaluate to `true` for the overall statement to evaluate to `true`.
If the first condition in an `||` statement evaluates to `true`, the second condition won't even be checked. Only if the first condition evaluates to `false`, the second one will be evaluated.

```js
if (day === 'Saturday' || day === 'Sunday') {
  console.log('Enjoy the weekend!');
} else {
  console.log('Do some work.');
}
```

The `!` *not operator* reverses, or *negates*, the value of a boolean:

```js
let excited = true;
console.log(!excited); // Prints false

let sleepy = false;
console.log(!sleepy); // Prints true
```

## Truthy and Falsy
Somethimes, you'll want to check if a variable exists and you won't necessary want it to equal a specific value. You'll only check to see if the variable has been assigned a value.

```js
let myVariable = 'I Exists!';
if (myVariable) {
  console.log(myVariable);
} else {
  console.log('The variable does not exist.');
}

// Prints 'I Exists!'
```

So which values are *falsy* or evaluate to `false` when checked as a condition? The list of falsy values includes:

* `0`
* Empty strings like `""` or `''`
* `null` which represent when there is no value at all
* `undefined` which represent when a declared variable lacks a value
* `NaN`, or Not a Number

```js
let numberOfApples = 0;
if (numberOfApples) {
  console.log('Let us eat apples!');
} else {
  console.log('No apples left!');
}

// Prints 'No apples left!'
```

## Truthy and Falsy Assignment
JavaScript assigns the truthy value to a variable if you use the `||` operator in your assignment:

`let defaultName = username || 'Stranger';`

Because `||` or statements check the left-hand condition first, the variable `defaultName` will be assigned the actual value of `username` if is truthy, and it will be assigned the value of `'Stranger'` if `username` is falsy. This concept is also referred to as *short-circuit evaluation*.

## Ternary Operator
We can use a *ternary operator* to simplify an `if...else` statement.

Take a look at the `if...else` statement example:

```js
let isNightTime = true;

if (isNightTime) {
  console.log('Turn on the lights!');
}else {
  console.log('Turn off the lights!');
}
```

We can use a *ternary operator* to perform the same functionality:

```js
isNightTime ? console.log('Turn on the lights!') : console.log('Turn off the lights!');
```

In the example above:

* The condition, `isNightTime`, is provided before the `?`.
* Two expresions follow the `?` and are separated by a colon `:`.
* If the condition evaluates to `true`, the first expression executes.
* If the condition evaluates to `false`, the second expression executes.

## Else If Statement
We can add more conditions to our `if...else` with an `else if` statement. The `else if` statement allows for more than two possible outcomes.

The `else if` statement always comes after the `if` statement and before the `else` statement. The `else if` statement also takes a condition.

```js
let stopLight = 'yellow';

if (stopLight === 'red') {
  console.log('Stop!');
} else if (stopLight === 'yellow') {
  console.log('Slow down.');
} else if (stopLight === 'green') {
  console.log('Go!');
} else {
  console.log('Caution, unknown!');
}
```

The `else if` statement allows you to have multiple possible outcomes. `if`/`else if`/`else` statements are read from top to bottom, so the first condition that evaluates to `true` from the top to bottom is the block that gets executed.

## The switch keyword
A switch statement provides an alternative syntax that is easier to read and write.

```js
let groceryItem = 'papaya';

switch (groceryItem) {
  case 'tomato':
    console.log('Tomatoes are $0.49');
    break;
  case 'lime':
    console.log('Limes are $1.49');
    break;
  case 'papaya':
    console.log('Papayas are $1.29');
    break;
  default:
    console.log('Invalid item');
    break;
}
```

* The `break` keyword tells the computer to exit the block and not execute any more code or check any other cases inside the code block. Note: Without the `break` keyword at the end of each case, the program would execute the code for all matching cases and the default code as well. 
* At the end of each `switch` statement, there is a `default` statement. If none of the `case`s are true, then the code in the default statement will run.