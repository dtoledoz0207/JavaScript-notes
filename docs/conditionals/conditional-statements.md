# Conditional Statements

* [What are Conditional Statements?](#What-are-Conditional-Statements?)
* [The if keyword](#The-if-keyword)


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

