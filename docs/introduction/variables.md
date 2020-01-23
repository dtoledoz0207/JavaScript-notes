# Variables

* [Variables](#Variables)
* [Create a Variable: var](#Create-a-Variable:-var)

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