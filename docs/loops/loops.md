# Loops

* [Loops](#Loops)
* [The For Loop](#The-For-Loop)


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