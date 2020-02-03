# Conditional Statements

* [What are Conditional Statements?](#What-are-Conditional-Statements?)
* [The if keyword](#The-if-keyword)
* [If...Else Statements](#If...Else-Statements)
* [Comparison Operators](#Comparison-Operators)


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

```
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

```
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
