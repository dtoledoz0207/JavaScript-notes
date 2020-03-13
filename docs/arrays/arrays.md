# Arrays

* [Arrays](#Arrays)
* [Create an Array](#Create-an-Array)
* [Accessing Elements](#Accessing-Elements)
* [Update Elements](#Update-Elements)
* [Arrays with let and const](#Arrays-with-let-and-const)
* [The .length property](#The-.length-property)
* [The .push() Method](#The-.push()-Method)
* [The .pop() Method](#The-.pop()-Method)


## Arrays
Arrays are JavaScript's way to making lists. Arrays can store any data types (including strings, numbers, and booleans). like lists, arrays are ordened, meaning each item has a numbered position.

Example of array:

```
let concepts = ['creating arrays', 'array structures', 'array manipulation']
```

## Create an Array
*array literal* is an one way we can create an array. An array literal creates an array by wrapping items in square brackets `[]`.

Arrays can store any data type, we can have an array that holds all the same data types or an array that holds different data types.

`['element example', 10, true]`

We can also save an array to a variable.

```
let newYearsResolutions = ['Keep a journal', 'Take a falconry class', 'Learn to juggle'];
```

## Accessing Elements
Each element in an array has a numbered position knows as its *index*. We can access individual items using their index.

Arrays in JavaScript are *zero-indexed*, meaning the positions start counting from `0` rather than `1`.

You can also access individual characters in a string using bracket notation and the index. For instance:

```
const hello = 'Hello World';
console.log(hello[6]);
// Ouput: W
```

## Update Elements
Once you have access to an element in an array, you can update its value.

```
let seasons = ['Winter', 'Sprint', 'Summer', 'Fall'];
seasons[3] = 'Autumn';
console.log(seasons);
// Output: ['Winter', 'Spring', 'Summer', 'Autumn']
```
The line, `seasons[3] = 'Autumn';` tells our program to change the item at index 3 of the `seasons` array to be `'Autumn'` instead of what is already there.

## Arrays with let and const
+ Variables declared with `let` can be reassigned.
+ Variables declared with `const` cannot be reassigned.

However, elements in array declared with `const` remain mutable. Meaning that we can change the contents of a `const` array, but cannot reassign a new array or a different value.

## The .length property
One of an array's built-in properties is `length` and it returns the number of items in the array.

```
const newYearsResolutions = ['Keep a journal', 'Take a falconry class'];

console.log(newYearsResolutions.length);
// Output: 2
```

## The .push() Method
`.push()` is a built-in JavaScript method that allows us to add items to the end of an array.

```
const itemTracker = ['item 0', 'item 1', 'item 2'];
itemTracker.push('item 3', 'item 4');

console.log(itemTracker);
// Output: ['item 0', 'item 1', 'item 2', 'item 3', 'item 4']
```

+ Notice that `.push()` changes, or *mutates*, `itemTracker`. You might also see `.push()` referred to as a *destructive* array method since it changes the initial array.

## The .pop() Method
Another array method, `.pop()`, removes the last item of an array.

```
const newItemTracker = ['item 0', 'item 1', 'item 2'];

const removed = newItemTracker.pop();

console.log(newItemTracker);
// Output: ['item 0', 'item 1']

console.log(removed);
// Output: item 2
```

+ `.pop()` returns the value of the last element and it can be stored in in a variable to be used for later.
+ `.pop()` is a method that mutates the initial array.