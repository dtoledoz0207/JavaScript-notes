# Introduction to JavaScript

* [Console](#Console)
* [Comments](#Comments)
* [Data Types](#Data-Types)
* [Arithmetic Operators](#Arithmetic-Operators)

## Console
The console is a panel that displays important messages, like errors, for developers. Much of the work the computer does with our code is invisible to us by default. If we want to see things appear on our screen, we can print, or log, to our console directly.

In JavaScript, the console keyword refers to an object, a collection of data and actions, that we can use in our code. Keywords are words that are built into the JavaScript language, so the computer will recognize them and treats them specially.

One action, or method, that is built into the console object is the .log() method. When we write `console.log()` what we put inside the parentheses will get printed, or logged, to the console.

`console.log('Hello World)`

## Comments
As we write JavaScript, we can write comments in our code that the computer will ignore as our program runs. These comments exist just for human readers.

Comments can explain what the code is doing, leave instructions for developers using the code, or add any other useful annotations.

1. A *single line comment* will comment out a single line and is denoted with two forward slashes `//` preceding it.

  ```
  // this is prints Hello World
  console.log('Hello World);
  ```
2. A *multi-line comment* will comment out multiple lines and is denoted with `/*`to begin the comment, and `*/` to end the comment.

  ```
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