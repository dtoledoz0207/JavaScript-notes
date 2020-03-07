# Scope

* [Scope](#Scope)
* [Block and Scope](#Block-and-Scope)
* [Global Scope](#Global-Scope)
* [Block Scope](#Block-Scope)


## Scope
An important idea in programming is *scope*.

Scope defines where variables can be accessed or referenced. While some variables can be accessed from anywhere within a program, other variable may only be available in a specific context.

## Block and Scope
A block is the code found inside a set of curly braces `{}`. Block help us group one or more statements together and serve as an important structural marker for our code.

Blocks difine the scope of variables.

```
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
```
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
```
const logSkyColor = () => {
  let color = 'blue';
  console.log(color); //blue
};

logSkyColor(); //blue
console.log(color); //ReferenceError
```
