# Functions

* [What are functions?](#What-are-functions?)
* [Function Declarations](#Function-Declarations)
* [Calling a function](#Calling-a-function)
* [Parameters and Arguments](#Parameters-and-Arguments)
* [Default parameters](#Default-parameters)
* [Return](#Return)



## What are functions?
In programing, we often use code to perform a specific task multiple times. Instead of rewriting the same code, we can group a block of code together and associate it with one task, the we can reuse that block of code whenever we need to perform the task again. We achieve this by creating a *function*. A function is a reusable block of code that groups together a sequence of statements to perform a specific task.

## Function Declarations
A function declaration consists of:

* The `function` keyword.
* The name of the function, or its identifier, followed by parentheses.
* A function body, or the block of statements required to perform a specific task, enclosed in the function's curly brackets, `{ }`.

We should also be aware of the *hosting* feature in JavaScript which allows access to function declarations before they're defined.

Since hoisting isn’t considered good practice, we simply want you to be aware of this feature.

## Calling a function
The code inside a function body runs, or *executes*, only when the function is *called*. To call a function in your code, you type the function name followed by parentheses.

```
function getGreeting() {
  console.log('Hello world!');
}

getGreeting();
```

## Parameters and Arguments
When declaring a function, we can specify its *parameters*. Parameters allow functions to accept inputs(s) and perform task using the input(s). We use paremeters as placeholders for information that will be passed to the function when it is called.

```
function calculateArea(width, height) {
  console.log(width * height);
}
```

When calling a function that has parameters, we specify the values in the parentheses that follow the function name. The values that are passed to the function when it is called are called *arguments*. Arguments can be passed to the function as values or variables.

`calculateArea(10, 6);`

## Default parameters
Feature added in ESC6.

Default parameters allow parameters to have a predetermined value in case there is no argument passed into the function or if the argument is `undefined` when called.

```
function greeting (name = 'stranger') {
  console.log(`Hello, ${name}!`);
}

greeting('Nick'); // Output: Hello, Nick!
greeting();       // Output: Hello, stranger!
```

By using a default parameter, we account for situations when an argument isn't passed into a function that is expecting an argument.

## Return
To pass back information from the function call, we use a return statement. To create a return statement, we use the `return` keyword followed by the value that we wish to return.

When a `return` statement is used in a function body, the execution of the function is stopped and the code that follows it will not be executed.

```
function rectangleArea(width, height) {
  if (width < 0 || height < 0) {
    return 'You need positive integers to calculate area!';
  }

  return width * height;
}
```

If an argument for `width` or `height` is less than `0`, then `rectangleArea()` will return `'You need positive integers to calculate area!'`. The second return statement `width * height` will not run.

