# Objects

* [Introduction to Objects](#Introduction-to-Objects)
* [Creating Object Literals](#Creating-Object-Literals)


## Introduction to Objects
With objects, we can open our code to more complex possibilities. We can use objects to model real-world things. We can use objects to build the data structures that make the web possible.

At their core, JavaScript objects are containers storing related data and functionality.

## Creating Object Literals
Objects can be assigned to variables just like any JavaScript type. We use curly braces, `{}`, to designate an *object literal:*

```js
let spaceship = {}; // spaceship is an empty object.
```

The data is organized into *key-values pairs*. A key is like a variable name that points to a location in memory that hold the value.

A key's values can be of any data type in the language including functions or other objects.

Keys are strings, but when we have a key that does not have any special characters in it, JavaScript allows us to omit the quotation marks.

```js
let spaceship = {
  'Fuel Type': 'diesel',
  color: 'silver'
};
```

The `spaceship` object has two properties `Fuel Type` and `color`. `Fuel Type` has quotation marks because it contains a space character.

