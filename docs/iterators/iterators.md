# Iterators

* [Introduction to Iterators](#Introduction-to-Iterators)
* [The .forEach() Method](#The-.forEach()-Method)
* [The .map() Method](#The-.map()-Method)
* [The .filter() Method](#The-.filter()-Method)
* [The .findIndex() Method](#The-.findIndex()-Method)


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

## The .map() Method
When `.mao()` is called on an array, it takes an argument of a callback function and returns a new array.

```js
const numbers = [1, 2, 3, 4, 5];

const bigNumbers = numbers.map(number => {
  return number * 10;
});

console.log(numbers); // Output: [1, 2, 3, 4, 5]
console.log(bigNumbers); // Output: [10, 20, 30, 40, 50]
```

`.map()` returns a new array.

+ `bigNumbers` will store the return value of calling `.map()` on `numbers`.
+ `numbers.map` will iterate through each element in the `numbers` array and pass the element into the callback function.
+ `return number * 10` is the code we wish to execute upon each element in the array. This will save each value from the `numbers` array, multiplied by `10`, to a new array.

## The .filter() Method
Like `.map()`, `.filter()` returns a new array. However, `.filter()` returns an arrays of elements after filtering out certain elements from the original array.

The callback function for the `.filter()` method should return `true` or `false` depending on the element that is passed to it. The elements that cause the callback function to return `true` are to the new array.

```js
const words = ['chair', 'music', 'pillow', 'brick', 'pen', 'door'];

const shortWords = words.filter(word => {
  return word.length < 6;
});

console.log(words); // Output: ['chair', 'music', 'pillow', 'brick', 'pen', 'door']
console.log(shortWords); // Output: ['chair', 'music', 'brick', 'pen', 'door']
```

+ `const shortWords =` declares a new variable that will store the returned array from invoking `.filter()`.
+ The callback function is an arrow function has a single parameter, `word`. Each element in the `words` array will be passed to this function as an argument.
+ `world.length < 6;` is the condition in the callback function. Any `word` from the `words` array thas has fewer than `6` characters will be added to the `shortWords` array.

## The .findIndex() Method
We sometimes want to find the location of an element in an array. That's where the `.findIndex()` method comes in.

`.findIndex()` on an array will return the index of the first element that evaluates to `true` in the callback function.

```js
const jumbledNums = [123, 25, 78, 5, 9];

const lessThanTen = jumbledNums.findIndex(num => {
  return num < 10;
});

console.log(lessThanTen); // Output: 3
```

+ `const lessThanTen = ` declares a new variable that stores the returned index number from invoking `.findIndex()`.
+ The callback function is an arrow function has a single parameter, `num`. Each element in the `jumbledNums` array will be passed to this function as an argument.
+ `num < 10;` is the condition that elements are checked against. `.findIndex()` will return the index of the first element which evaluates to `true` for that condition.

if there isn't a single element in the array that satisfies the condition in the callback, then `.findIndex()` will return `-1`.

```js
const greaterThan1000 = jumbledNums.findIndex(num => {
  return num > 1000;
});

console.log(greaterThan1000); // Output: -1
```