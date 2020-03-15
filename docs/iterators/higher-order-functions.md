# Higher-Order Functions

* [Introduction](#Introduction)
* [Functions as Data](#Functions-as-Data)


## Introduction
In programming, we can accomplish "abstraction" by writing functions. In addition to allowing us to reuse our code, functions help to make clear, readable programs.

We are going to learn about another way to add a level of abstraction to our programming: *higher-order functions.* *Higher-order functions* are functions that accept other functions as arguments and/or return functions as output. This enables us to build abstractions on other abstractions, just like "We hosted a birthday party" is an abstraction that may build on the abstraction "We made a cake".

## Functions as Data
JavaScript functions behave like any other data type in the language; we can assingn functions to variables, and we can reassign them to new variables.

```js
const announceThatIAmDoingImportantWork = () => {
    console.log("I’m doing very important work!");
};
```

We can re-assign the function to a variable with a suitably short name:

```js
const busy = announceThatIAmDoingImportantWork;

busy();
```

`busy` is a variable that holds a *reference* to our original function. Our new `busy()` function can be invoked with parentheses as if that was the name we originally gave our function.

Notice how we assign `announceThatIAmDoingImportantWork` without parentheses as the value to the `busy` variable. We want to assign the value of the function itself, not the value it returns when invoked.

In JavaScript, functions are *first class objects*. This means that, like other objects you've encountered, JavaScript functions can have properties and methods. You can see more about the methods and properties of functions [in the documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function).