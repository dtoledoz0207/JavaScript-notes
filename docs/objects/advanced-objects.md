# Advanced Objects

* [The this Keyword](#The-this-Keyword)


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