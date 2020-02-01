# Variables

* [Variables](#Variables)
* [Create a Variable: var](#Create-a-Variable:-var)
* [Create a Variable: let](#Create-a-Variable:-let)
* [Create a Variable: const](#Create-a-Variable:-const)
* [Mathematical Assignment Operators](#Mathematical-Assignment-Operators)


## Variables
In programming, a variable is a container for a value. You can think of variables as little containers for information that live in a computer’s memory.

Variables label and store data in memory. There are only a few things you can do with variables:

  1. Create a variable with descriptive name.
  2. Store or update information stored in a variable.
  3. Reference or "get" information stored in a variable.

## Create a Variable: var
There were a lot of changes introduced in the ES6 version of JavaScript in 2015. One of the biggest changes was two new keywords, `let` and `const`, to create, or *declare*, variables. Prior to the ES6, programmers could only use the `var` keyword to declare variables.

`var myName = 'David';`

  1. `var`, short for variable, is a JavaScript *keyword* that creates, or *declares* a new variable.
  2. `myName` is the variable's name. Capitalizing in this way is a standard convention in JavaScript called *camel casing*.
  3. `=` is the *assignment operator*. It assigns the value `'David'` to the variable `myName`.
  4. `'David'` is the *value* assigned `=` to the variable `myName`. You can also say that the `myName` variable is *initialized* with a value of `'David'`.

There are a few general rules for naming variables:

  * Variable names cannot start with numbers.
  * Variable names are case sensitive.
  * Variable names cannot be the same as *keywords*. For a comprehensive list of keywords check out [MDN's keyword documentation.](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#Keywords)

## Create a Variable: let
The `let` keyword signals that the variable can be reassigned a different value.

  ```
  let meal = 'Tacos';
  console.log(meal); // Prints 'Tacos'
  meal = 'Pizza';
  console.log(meal); // Prints 'Pizza'
  ```
When we use `let` and even `var`, we can declare a variable without assigning the variable a value. In such a case, the variable will be automatically initialized with a value of `undefined`.

  ```
  let price;
  console.log(price); // Prints undefined
  price = 350;
  console.log(price); // Prints 350
  ```

## Create a Variable: const
Just like with `var` and `let` you can store any value in a `const` variable.

`const myName = 'David';`

However, a `const` variable cannot be reassigned because it is *constant*. If you try to reassing a `const` variable, you'll get a `TypeError`.

Constant variables *must* be assigned a value when declared. If you try to declare a `const` variable without a value, you'll get a `SyntaxError`.

## Mathematical Assignment Operators

```
let w = 4;
w += 1;

console.log(w); // Output: 5
```
We're performing the mathematical operation of the first operator `+` using the number to the right, then reassigning `w` to the computed value.

We also have access to other mathematical assignment operators: `-=`, `*=`, and `/=`.

```
let x = 20;
x -= 5; // Can be written as x = x - 5
console.log(x); // Output: 15

let y = 50;
y *= 2; // Can be written as y = y * 2;
console.log(y); // Output: 100

let z = 8;
z /= 2; // Can be written as z = z/2;
console.log(z); // Output: 4
```