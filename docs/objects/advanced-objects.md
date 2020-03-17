# Advanced Objects

* [The this Keyword](#The-this-Keyword)
* [Arrow Functions and this](#Arrow-Functions-and-this)
* [Privacy](#Privacy)


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