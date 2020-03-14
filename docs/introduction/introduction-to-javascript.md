# Introduction to JavaScript

* [Console](#Console)
* [Comments](#Comments)
* [Data Types](#Data-Types)
* [Arithmetic Operators](#Arithmetic-Operators)
* [String Concatenation](#String-Concatenation)
* [Properties](#Properties)
* [Methods](#Methods)
* [Built-in Objects](#Built-in-Objects)

## Console
The console is a panel that displays important messages, like errors, for developers. Much of the work the computer does with our code is invisible to us by default. If we want to see things appear on our screen, we can print, or log, to our console directly.

In JavaScript, the console keyword refers to an object, a collection of data and actions, that we can use in our code. Keywords are words that are built into the JavaScript language, so the computer will recognize them and treats them specially.

One action, or method, that is built into the console object is the .log() method. When we write `console.log()` what we put inside the parentheses will get printed, or logged, to the console.

`console.log('Hello World)`

## Comments
As we write JavaScript, we can write comments in our code that the computer will ignore as our program runs. These comments exist just for human readers.

Comments can explain what the code is doing, leave instructions for developers using the code, or add any other useful annotations.

1. A *single line comment* will comment out a single line and is denoted with two forward slashes `//` preceding it.

  ```js
  // this is prints Hello World
  console.log('Hello World);
  ```
2. A *multi-line comment* will comment out multiple lines and is denoted with `/*`to begin the comment, and `*/` to end the comment.

  ```js
  /* 
  This block
  is a comment.
  */
  ```

## Data Types
*Data types* are the classifications we give to the differents kinds of data that we use in programming. In JavaScript, there are seven fundamental data types:

1. *Number*: Any number, including numbers with decimals: `4`, `8`, `1516`, `23.42`.
2. *String*: Any grouping of characters on your keyboard (letters, numbers, spaces, symbols, etc.) surrounded by single quotes:
`' ... '`.
3. *Boolean*: This data type only has two possible values `true` or `false`.
4. *Null*: This data type represents the intentional absence of a value, and is represented by the keyword `null`.
5. *Undefined*: This data type is denoted by the keyword `undefined`. It also represents the absence of value though it has a different use than `null`.
6. *Symbol*: A newer feature to the language, symbols are unique identifiers, useful in more complex coding.

7. *Object*: Collection of related data.

The first 6 of those types are considered primitive data types. They are the most basic data types in the language.

## Arithmetic Operators
An *operator* is a character that performs a task in our code. JavaScript has several built-in in *arithmetic operators*, that allow us to perform mathematical calculations on numbers. These include the following operators and their corresponding symbols:

1. Add: `+`
2. Subtract: `-`
3. Multiply: `*`
4. Divide: `/`
5. Remainder: `%`

The remainder operator, sometimes called *modulo*, returns the number that remains after the right-hand number divides into the left-hand number as many times as it evenly can.

## String Concatenation
The process of appending one string to another is called *concatenation*.
The computer will join the strings exactly, so we needed to make sure to include the space we wanted between the two strings.
  ```js
  console.log('I love to ' + 'code.');  // Prints 'I love to code.'
  console.log('front ' + 'space');      // Prints 'front space';
  console.log('middle' + ' ' + 'space'); // Prints 'middle space'
  ```

## Properties
When you intruduce a new piece of data into JavaScript program, the browser saves it as an instance of the data type.
Every string instance has a property called `length` that store the number of characters in that string.

  `console.log('Hello'.length); // Prints 5`

The `.` is another operator, we call it *dot operator*.

## Methods
Methods are actions we can perform.

We *call*, or use, these methods by appending an instance with period(the dot operator), the name of the method, and opening and closing parentheses.

When we use `console.log()` we're calling the `.log()` method on the `console`object.

  ```js
  console.log('hello'.toUpperCase()); // Prints 'HELLO'
  console.log('Hey'.startsWith('H')); // Prints true
  console.log('   Remove whitespaces    '); // Prints 'Remove whitespaces'
  ```

The methods can receive elements as an input, or *argument*, between the parentheses, like `.startsWith('H')`.

## Built-in Objects
In addition to console, there are other **objects built into JavaScript**.

For example, if you wanted to perform more complex mathematical operations that arithmetic, JavaScript has the built-in `Math` object.

The great thing about objects is that they have methods. In the next example we call the `.random()` method from the built-in Math object:

  ```js
  console.log(Math.random());
  // Prints a random number between 0 and 1
  ```
To generate a random number between 0 and 50, we could multiply this result by 50, like so:

  ```js
  console.log(Math.random() * 50);
  // Prints a random number between 0 and 50
  ```
To ensure the answer is a whole number, we can take advantage of another useful `Math` method called `Math.floor()`.

`Math.floor()` takes a decimal number, and rounds down to the nearest whole number.

```js
console.log(Math.floor(Math.random() * 50));
// Prints a integer number between 0 and 50
```

Use the `.ceil()` method to calculate the smallest integer greater than or equal to `43.8`.

```js
console.log(Math.ceil(43.8));
// Prints 44
```

Use the `isInteger()` method from the `Number` object to check if `2017` is an integer.

```js
console.log(Number.isInteger(34.2));
// Prints false
```