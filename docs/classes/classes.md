# Classes

* [Introduction to Classes](#Introduction-to-Classes)
* [Constructor](#Constructor)
* [Instance](#Instance)


## Introduction to Classes
JavaScript is an *object-oriented programming* (OOP) language we can use to model real-world items. Classes are a tool that developers use to quickly produce similar objects.

Classes are great way to reduce duplicate code and debugging time.

```js
class Dog {
  constructor(name) {
    this._name = name;
    this._behavior = 0;
  }

  get name() {
    return this._name;
  }

  get behavior() {
    return this._behavior;
  }

  incrementBehavior() {
    this.behavior ++;
  }
}

const halley = new Dog('Halley');

console.log(halley.name); // Prints: Halley
console.log(halley.behavior); // Prints: 0

halley.incrementBehavior();
console.log(halley.behavior); // Prints: 1
```

## Constructor
JavaScript calls the `constructor()` method every time it creates a new *instance* of a class.

```js
class Dog {
  constructor(name) {
    this.name = name;
    this.behavior = 0;
  }
}
```

+ `Dog` is the name of our class. By convention, we capitalize and CamelCase class names.
+ JavaScript will invoke the `constructor()` method every time we create a new instance of out `Dog` class.
+ This `constructor()` method accepts one argument, `name`.
+ Inside the constructor method, we use the `this` keyword. In the context of a class. `this` refers to an instance of that class. In the `Dog` class, we use `this` to set the value of the Dog instance's `name` property to the `name` argument.
+ The `behavior` property is always initialized to zero.

## Instance
An *instance* is an object that contains the property names and methods of a class, but with unique property values.

```js
class Dog {
  constructor(name) {
    this.name = name;
    this.behavior = 0,
  }
}

const halley = new Dog('Halley'); // Create new Dog instance

console.log(halley.name); // Output: 'Halley'
```

+ We create a new variable named `halley` that will store an instance of our `Dog` class.
+ We use  the `new` keyword to generate a new instance of the `Dog` class. The `new` keyword calls the `constructor()`, runs the code inside of it, and then returns the new instance.
+ Finally, we log the value saved to the `name` key in our `halley` object.