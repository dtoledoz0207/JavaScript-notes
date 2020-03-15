# Iterators

* [Introduction to Iterators](#Introduction-to-Iterators)
* [The .forEach() Method](#The-.forEach()-Method)


## Introduction to Iterators
The built-in JavaScript array methods that help us iterate are called *iteration methods*, at times referred to as *iterators*.

Iterators are methods called in arrays to manipulate elements and return values.

## The .forEach() Method
The first iteration method is `.forEach()`. `.forEach()` will execute the same code for each element of an array.

![image info](../images/foreach.png)

+ `groceries.forEach()` calls the `forEach` method on the `groceries` array.
+ `.forEach()` takes an argument of callback function. Remember, a callback function is a function passed as an argument into another function.
+ `.forEach()` loops through the array and executes the callback function for each element. During each execution, the current element is passed as an argument to the callback function.
+ The return value for `.forEach()` will always be `undefined`.

Another way to pass a callback for `.forEach()` is using arrow function syntax.
```js
groceries.forEach(groceryItem => console.log(groceryItem));
```

We can also define a function beforehand to be used as the callback function.
```js
function printGrocery(element) {
  console.log(element);
}

groceries.forEach(printGrocery);
```

`.forEach()` example:
```js
const fruits = ['mango', 'papaya', 'pineapple', 'apple'];

fruits.forEach(fruit => {
  console.log('I want to eat a ' + fruit);
});
```

Output:
```js
I want to eat a mango
I want to eat a papaya
I want to eat a pineapple
I want to eat a apple
```
