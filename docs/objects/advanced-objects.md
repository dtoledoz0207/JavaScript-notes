# Advanced Objects

* [The this Keyword](#The-this-Keyword)
* [Arrow Functions and this](#Arrow-Functions-and-this)
* [Privacy](#Privacy)
* [Getters](#Getters)
* [Setters](#Setters)
* [Factory Functions](#Factory-Functions)
* [Property Value Shorthand](#Property-Value-Shorthand)


## The this Keyword
Objects are collections of related data and functionality. We store that functionality in methods on our objects.

What if we wanted to add a new method to our `goat` object called `.diet()` that prints the `goat`'s `dietType`?

```js
const goat = {
    dietType: 'herbivore',
    makeSound() {
        console.log('baaa');
    },
    diet() {
        console.log(dietType);
    }
};

goat.diet();
// Output will be "ReferenceError: dietType is not defined"
```

This error is because inside the scope of the `.diet()` method, we don't automatically have access to other properties of the `goat` object.

If we change the `.diet()` method to use `this`, the `.diet()` works!

```js
const goat = {
    dietType: 'herbivore',
    makeSound() {
        console.log('baaa');
    },
    diet() {
        console.log(this.dietType);
    }
};

goat.diet();
// Output: herbivore
```

The `this` keyword references the *calling object* which provides access to the calling object's properties. In the example above, the calling object is `goat` and by using `this` we're accessing the `goat` object itself, and then the `dietType` property of `goat` by using property dot notation.

## Arrow Functions and this
There is a problem with `this` when we start using arrow functions for methods.

```js
const goat = {
    dietType: 'herbivore',
    makeSound() {
        console.log('baaa');
    },
    diet: () => {
        console.log(this.dietType);
    }
};

goat.diet(); // Prints undefined
```

Arrow functions inherently *bind*, or tie, an already defined `this` value to the function itself is NOT the calling object. In the example above, the value of `this` is the *global object*, or an object that exist in the global scope, which doesn't have a `dietType` property and therefore returns `undefined`.

The key takeaway from the example above is to *avoid* using arrow functions when using `this` in a method.

## Privacy
Accessing and updating properties is fundamental in working with objects. However, there are cases in which we don't want other code simply accessing and updating an object's properties. When discussing *privacy* in objects, we define it as the idea that only certain properties should be mutable or able to change in value.

JavaScript doesn't have privacy built-in for objects.

JavaScript developers follow naming conventions that signal to other developers how to interact with a property. One common convention is to place an underscore `_` before the name of a property to mean that the property should not be altered.

```js
const bankAccount = {
    _amount: 1000
};
```

In the example above, the `_amount` is not intended to be directly manipulated.
Even so, it is still possible to reassing `_amount`:

```js
bankAccount._amount = 1000000;
```

There are some method to do that, called *getters* and *setters*. Getters can return the value of internal properties and setters can safely reassing property values.

## Getters
*Getters* are methods that get and return the internal properties of an object.

```js
const person = {
    _firstName: 'John',
    _lastName: 'Doe',
    get fullName() {
        if (this._firstName && this._lastName) {
            return `${this._firstName} ${this._lastName}`;
        } else {
            return 'Missing a first name or a last name.';
        }
    }
};

// To call the getter method:
person.fullName; // 'John Doe'
```

+ We use the `get` keyword followed by a function.
+ We use an `if...else` conditional to check if both `_firstName` and `_lastName` exist and then return a different value depending on the result.
+ We can access the calling object's internal properties using `this`.
+ In the last line we call `fullName` on person. In general, getter methods do not need to be called with a set of parentheses. Syntactically, it looks like we're accessing a property.

Another thing to keep in mind when using getter (and setter) methods is that properties cannot share the same name as the getter/setter function. If we do so, then calling the method will result in an infinite call stack error.

## Setters
We can also create *setter* methods which reassing values of existing properties within an object.

```js
const robot = {
  _model: '1E78V2',
  _energyLevel: 100,
  _numOfSensors: 15,
  get numOfSensors(){
    if(typeof this._numOfSensors === 'number'){
      return this._numOfSensors;
    } else {
      return 'Sensors are currently down.'
    }
  },
  set numOfSensors(num) {
    if (typeof num === 'number' && num >= 0) {
      this._numOfSensors = num;
    } else {
      console.log('Pass in a number that is greater than or equal to 0');
    }
  }
};

robot.numOfSensors = 100;
console.log(robot.numOfSensors); // Output: 100

robot.numOfSensors = '3'; // Output: Pass in a number that is greater than or equal to 0
```

+ When we use the setter method, only values that are numbers will reassign `this._numOfSensors`

Setter methods like `numOfSensors` do not need to be called with a set of parentheses. Syntactically, it looks like we’re reassigning the value of a property.

## Factory Functions
A factoty function is a function that returns an object and can be reused to make multiple object instances.

Factory functions can also have parametes allowing us to customize the object that gets returned.

```js
const robotFactory = (model, mobile) => {
  return {
    model: model,
    mobile: mobile,
    beep() {
      console.log('Beep Boop');
    }
  }
}

const tinCan = robotFactory('P-500', true);

tinCan.beep(); // Output: 'Beep Boop'
```

Now we have a `tinCan` object as a result of calling `robotFactory()` with the needed arguments.

With `robotFactory` in place, we don't have to create an object literal every time we need a new robot. Instead, we can invoke the `robotFactory` function with the necessary arguments.

## Property Value Shorthand
ES6 introduced some new shortcuts for assigning properties to variables known as *destructuring*.

```js
const monsterFactory = (name, age) => {
  return {
    name: name,
    age: age
  }
};
```

Now we can use destructuring technique, called *property value shorthand*, The example below works exactly like the example above:

```js
const monsterFactory = (name, age) => {
  return {
    name,
    age
  }
};
```