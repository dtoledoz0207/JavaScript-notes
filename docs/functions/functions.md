# Functions

* [What are functions?](#What-are-functions?)
* [Function Declarations](#Function-Declarations)
* [Calling a function](#Calling-a-function)



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