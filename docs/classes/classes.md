# Classes

* [Introduction to Classes](#Introduction-to-Classes)


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