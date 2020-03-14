# Scope

* [Scope](#Scope)
* [Block and Scope](#Block-and-Scope)
* [Global Scope](#Global-Scope)
* [Block Scope](#Block-Scope)
* [Scope Pollution](#Scope-Pollution)


## Scope
An important idea in programming is *scope*.

Scope defines where variables can be accessed or referenced. While some variables can be accessed from anywhere within a program, other variable may only be available in a specific context.

## Block and Scope
A block is the code found inside a set of curly braces `{}`. Block help us group one or more statements together and serve as an important structural marker for our code.

Blocks difine the scope of variables.

```js
const city = 'New York City';

const logCitySkyline = () => {
  let skyscraper = 'Empire State Building';
  return 'The stars over the ' + skyscraper + ' in ' + city;
}

console.log(logCitySkyline()) // Prints The stars over the Empire State Building in New York City
```

`logCitySkyline()` function is able to access both variables without any problems.

## Global Scope
In *global scope*, variables are declared outside of block. These variables are called *global variables*. Because global variables are not bound inside a block, they can be accessed by any code in the program, including code in blocks.

Example of global scope:
```js
const color = 'blue';

const returnSkyColor = () => {
  return color; //blue
}

console.log(returnSkyColor()); //blue
```

## Block Scope
When a variable is definied inside a block, it is only accessible to the code within the curly braces `{}`. We say that variable has *block scope* because it is *only* accessible to the lines of the code within that block.

Variables that are declared with block scope are known as *local variables*.

Block scope example:
```js
const logSkyColor = () => {
  let color = 'blue';
  console.log(color); //blue
};

logSkyColor(); //blue
console.log(color); //ReferenceError
```

## Scope Pollution
*Scope pollution* is when we have too many global variables that exist in the global namespaces, or when we reuse variables across different scopes. Scope pollution makes it difficult to keep track of or different variables and set us up for potencial accidents.
For example, globally scoped variables can collide with other variables that are more locally scoped, causing unexpected behavior in our code.

Example of scope pollution in practice:
```js
let num = 50;

const logNum = () => {
  num = 100; // Take note of this line of code
  console.log(num);
};

logNum(); // Prints 100
console.log(num); // Prints 100
```
While it's important to know what global scope is, it's best practice to not define variables in the global scope.