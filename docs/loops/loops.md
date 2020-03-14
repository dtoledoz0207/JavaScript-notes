# Loops

* [Loops](#Loops)
* [The For Loop](#The-For-Loop)
* [Looping in Reverse](#Looping-in-Reverse)
* [Looping through Arrays](#Looping-through-Arrays)
* [Nested Loops](#Nested-Loops)


## Loops
A *Loop* is a programming tool that repeats a set of instructions until a specified condition, called a *stopping condition* is reached.

The generic term *iterate* is used when referring to loops; iterate simply means "to repeat".

Loops allow us to create efficient code that automates processes to make scalable, manageable programs.

Loops iterate or repeat an action until a specefic condition is met. When the condition is met, the loop stop and the computer moves on to the next part of the program.

## The For Loop
Loops allow us to tell computers to repeat a given block of code on its own. One way to give computers these instructions is with a `for` loop.

The typical `for` loop includes an *iterator variable* that usually appears in all three expressions. The iterator variable is initialized, checked against the stopping condition, and assigned a new value on each loop iteration.

A `for` loop contains three expressions separated by `;` inside the parentheses:

1. an *initialization* starts the loop and can also be used to declare the iterator variable.
2. a *stopping condition* is the condition that the iterator variable is evaluated against if the condition evaluates to `true` the code block will run, and if it evaluates to `false` the code will stop.
3. an *iteration statement* is used to update the iterator variable on each loop.

`for` loop syntax:
```
for (let counter = 0; counter < 4; counter++) {
  console.log(counter);
}
```
Output:
```
0
1
2
3
```
+ The initialization is `let counter = 0`.
+ The stopping condition is `counter < 4`.
+ The iteration statement is `counter++`.

## Looping in Reverse
To run a backward `for` loop, we must:
+ Set the iterator variable to the highest desired value in the initialization expression.
+ Set the stopping condition for when the iterator variable is less than the desired amount.
+ The iterator should decrease in intervals after each iteration.

Loop in reverse:
```
for (let counter = 3); counter >= 0; counter--) {
  console.log(counter);
}
```

Output:
```
3
2
1
0
```

## Looping through Arrays
To loop through each element in an array, a `for` loop should use the array's `.length` property in its condition.

`for` loops iterate on arrays:
```
const animals = ['Dog', 'Cat', 'Turtle'];
for (let i = 0; i < animals.length; i++) {
  console.log(animals[i]);
}
```
Output:
```
Dog
Cat
Turtle
```
When we use `i` to iterate through arrays we can think of it as being short-hand for the word **i**ndex.

Notice how our stopping condition checks that `i` is less than `animals.length`. Remember that arrays ere zero-indexed, the index of the last element of an array is equivalent to the length of that array minus 1.

## Nested Loops
When we have a loop running inside another loop, we call that a *nested loop*. One use for a nested `for` loop is to compare the elements in two arrays. For each round of the outer `for` loop, the inner `for` loop will run completly.

```
let bobsFollowers = ['Daniel', 'Juan', 'Mateo', 'Luis'];

let tinasFollowers = ['Juan', 'Mateo', 'Maria'];

let mutualFollowers = [];

for (let i = 0; i < bobsFollowers.length; i++) {
  for (let j = 0; j < tinasFollowers.length; j++) {
    if (bobsFollowers[i] === tinasFollowers[j]) {
      mutualFollowers.push(tinasFollowers[j]);
    }
  }
}

console.log(mutualFollowers);
// Output: ['Juan', 'Mateo']
```