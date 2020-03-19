# Classes

* [Introduction to Classes](#Introduction-to-Classes)
* [Constructor](#Constructor)
* [Instance](#Instance)
* [Methods](#Methods)
* [Method Calls](#Method-Calls)
* [Inheritance I](#Inheritance-I)
* [Inheritance II](#Inheritance-II)
* [Inheritance III](#Inheritance-III)
* [Inheritance IV](#Inheritance-IV)


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

## Methods
Class method and getter syntax is the same as it is for objects **except you can not include commas between methods.**

```js
class Surgeon {
  constructor(name, department) {
    this._name = name;
    this._department = department;
    this._remainingVacationDays = 20;
  }

  get name() {
    return this._name;
  }

  get department() {
    return this._department;
  }

   get remainingVacationDays() {
    return this._remainingVacationDays;
  }
  
  takeVacationDays(daysOff) {
    this._remainingVacationDays -= daysOff;
  }
}
```

In the example, we add getter methods for `name`, `department` and `remainingVacationDays`.

Notice, we also prepended our property names with underscores (`_name`, `_department` and `_remainingVacationDays`), which indicate these properties should not be accessed directly.

Under the getters we add a method named `.takeVacationDays(daysOff)` that accept one argument named `daysOff`.

And inside this method, subtract `daysOff` from the number saved to `_remainingVacationDays` and sets `_remainingVacationDays` to the result.

## Method Calls
The syntax for calling methods and getters on an instance is the same as calling them on an object, append the instance with a period, then the property or method name. **For methods, you must also include opening and closing parentheses.**

```js
class Surgeon {
  constructor(name, department) {
    this._name = name;
    this._department = department;
    this._remainingVacationDays = 20;
  }

  get name() {
    return this._name;
  }

  get department() {
    return this._department;
  }

  get remainingVacationDays() {
    return this._remainingVacationDays;
  }
  
  takeVacationDays(daysOff) {
    this._remainingVacationDays -= daysOff;
  }
}

const surgeonCurry = new Surgeon('Curry', 'Cardiovascular');
const surgeonDurant = new Surgeon('Durant', 'Orthopedics');

console.log(surgeonCurry.name); // Prints: 'Curry'
surgeonCurry.takeVacationDays(3);
console.log(surgeonCurry.remainingVacationDays); // Prints: 17
```

## Inheritance I
When multiple classes share properties or methodsm they become candidates for *inheritance*, a tool developers use to decrease the amount of code they need to write.

With inheritance, you can create a *parent* class (also known as a superclass) with properties and methods that multiple *child* classes (also known as subclasses) share. The child classes inherit the properties and methods from their parent class.

Let's abstract the shared properties and methods from our `Cat` and `Dog` classes into a parent class called `Animal`.

```js
class Animal {
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
    this._behavior++;
  }
}
```

In the example, the `Animal` class contains the properties and methods that the `Cat` and `Dog` classes share (`name`, `behavior`, `.incrementBehavior()`).

## Inheritance II
Parent class:

```js
class HospitalEmployee {
  constructor(name) {
    this._name = name;
    this._remainingVacationDays = 20;
  }

  get name() {
    return this._name;
  }

  get remainingVacationDays() {
    return this._remainingVacationDays;
  }

  takeVacationDays(daysOff) {
    this._remainingVacationDays -= daysOff;
  }
}
```

## Inheritance III
We've abstracted the shared properties and methods of our `Nurse` and `Doctor` classes into a parent class called `HospitalEmployee`.

```js
class HospitalEmployee {
  constructor(name) {
    this._name = name;
    this._remainingVacationDays = 20;
  }
  
  get name() {
    return this._name;
  }
  
  get remainingVacationDays() {
    return this._remainingVacationDays;
  }
  
  takeVacationDays(daysOff) {
    this._remainingVacationDays -= daysOff;
  }
}
```

Now that we have these shared properties and methods in the parent `HospitalEmployee` class, we can extend them to the subclass `Nurse`.

```js
class Nurse extends HospitalEmployee {
  constructor(name, certifications) {
    super(name);
    this._certification = certification;
  }
}

const nurseOlynyk = new Nurse('Olynyk', ['Trauma', 'Pediatrics']);
```

In the example, we create a new class named `Nurse` that extends the `HospitalEmployee` class. Let's pay special attention to our new keywords: `extends` and `super`.

+ The `extends` keyword makes the methods of the hospitalEmployee class available inside the nurse class.
+ The constructor, called when you create a new `Nurse` object, accepts two arguments, `name` `certification`.
+ The `super` keyword calls the constructor of the parent class. In this case, `super(name)` passes the name argument of the `Nurse` class to the constructor of the `HospitalEmployee` class. When the `HospitalEmployee` constructor runs, it sets `this._name = name;` for new `Nurse` instances.
+ `certifications` is a new property that is unique to the `Nurse` class, so we set it in the `Nurse` constructor.

+ In a `constructor()`, you must always call `super` method before you can use the `this` keyword, if you do not, JavaScript will throw a reference error. To avoid reference errors, it is best practice to call `super` on the first line of subclass constructors.

## Inheritance IV
When we call `extends` in a class declaration, all of the parent methods are available to the child class.

```js
class HospitalEmployee {
  constructor(name) {
    this._name = name;
    this._remainingVacationDays = 20;
  }
  
  get name() {
    return this._name;
  }
  
  get remainingVacationDays() {
    return this._remainingVacationDays;
  }
  
  takeVacationDays(daysOff) {
    this._remainingVacationDays -= daysOff;
  }
}

class Nurse extends HospitalEmployee {
  constructor(name, certification) {
    super(name);
    this._certification = certification;
  }
}
```

In the example, `Nurse` class extends `HospitalEmployee`. As a result, the `Nurse` class has access to the `HospitalEmployee` getters and the `.takeVacationDays(dayOff)` method.

```js
nurseOlynyk = new Nurse('Olynyk', ['Trauma','Pediatrics']);

nurseOlynyk.takeVacationDays(5);
console.log(nurseOlynyk.remainingVacationDays);
// Prints: 15
```