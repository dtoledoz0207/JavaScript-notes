# Objects

* [Introduction to Objects](#Introduction-to-Objects)
* [Creating Object Literals](#Creating-Object-Literals)
* [Accessing Properties](#Accessing-Properties)
* [Bracket Notation](#Bracket-Notation)
* [Property Assignment](#Property-Assignment)
* [Methods](#Methods)
* [Nested Objects](#Nested-Objects)
* [Pass By Reference](#Pass-By-Reference)


## Introduction to Objects
With objects, we can open our code to more complex possibilities. We can use objects to model real-world things. We can use objects to build the data structures that make the web possible.

At their core, JavaScript objects are containers storing related data and functionality.

## Creating Object Literals
Objects can be assigned to variables just like any JavaScript type. We use curly braces, `{}`, to designate an *object literal:*

```js
let spaceship = {}; // spaceship is an empty object.
```

The data is organized into *key-values pairs*. A key is like a variable name that points to a location in memory that hold the value.

A key's values can be of any data type in the language including functions or other objects.

Keys are strings, but when we have a key that does not have any special characters in it, JavaScript allows us to omit the quotation marks.

```js
let spaceship = {
  'Fuel Type': 'diesel',
  color: 'silver'
};
```

The `spaceship` object has two properties `Fuel Type` and `color`. `Fuel Type` has quotation marks because it contains a space character.

## Accessing Properties
There are two ways we can access an object's property. The first way is - dot notation, `.`.

```js
let spaceship = {
  homePlanet: 'Earth',
  color: 'silver'
};
spaceship.homePlanet; // Returns 'Earth'
spaceship.color; // Returns 'silver'
```

If we try to access a property that does not exist on that object, `undefined` will returned.

```js
spaceship.favoriteIcecream; // Returns undefined
```

## Bracket Notation
The second way to access a key's value is by using bracket notation `[ ]`.

To use bracket notation to access an object's property, we pass in the property name (key) as a string.

We **must** use brackets notation when accessing key that have numbers, spaces, or special characters in them. Without bracket notation in these situations, our code would throw an error.

```js
let spaceship = {
  'Fuel Type': 'Turbo Fuel',
  'Active Duty': true,
  homePlanet: 'Earth',
  numCrew: 5
};

spaceship['Active Duty']; // Returns true
spaceship['Fuel Type']; // Returns 'Turbo Fuel'
spaceship['numCrew']; // Returns 5
spaceship['!!!!!!!!!'] // Returns undefined
```

With bracket notation we can also use a variable inside the brackets to select the keys of an object. This can be especially helpful when working with functions:

```js
let returnAnyProp = (objectName, propName) => objectName[propName];

returnAnyProp(spaceship, 'homePlanet'); // Returns 'Earth'
```

## Property Assignment
Objects are *mutable* meaning we can update them after we create them.

We can use either dot notation `.` or bracket notation `[]`, and the assignment operator `=`, to add new key-value pairs to an object or change an existing property.

```js
spaceship['Fuel Type'] = 'vegetable oil';
spaceship.color = 'gold';
```

One of two things can happen with property assignment:
 
 + If the property already exist on the object. whatever value it held before will be replaced with the newly assigned value.
 + If there was no property with that name, a new property will be added to the object.

It's important to know that although we can't reassign an object declared with `const`, we can still mutate it, meaning we can add new properties and change the properties that are there.

```js
const spaceship = {type: 'shuttle'};
spaceship = {type: 'alien'}; // TypeError: Assignment to constant variable.

spaceship.type = 'alien'; // Changes the value of the type property

spaceship.speed = 'Mach 5'; // Creates a new key of 'speed' with a value of 'Mach 5'
```

Also we can delete a property from an object with the `delete` operator.

```js
const spaceship = {
  'Fuel Type': 'Turbo Fuel',
  homePlanet: 'Earth',
  mission: 'Explore the universe'
};

delete spaceship.mission; // Removes the mission property
```

## Methods
When the data stored on an object is a function we call that a *method*. A property is what an object  has, while a method is what an object does.

We can include methods in our object literals by creating ordinary, comma-separated key-values pairs. The key serves as our method's name, while the value is an anonymous function expression.

```js
const alienShip = {
  invade: function () {
    console.log('Hello! We have come to dominate your planet. Instead of Earth, it shall be called New Xaculon.')
  }
};
```

With the new method syntax introduced in ES6 we can omit the colon and the `function` keyword.

```js
const alienShip = {
  invade() {
    console.log('Hello! We have come to dominate your planet. Instead of Earth, it shall be called New Xaculon.')
  }
};
```

Example how to invoke an Object method:
```js
alienShip.invade(); // Prints 'Hello! We have come to dominate your planet. Instead of Earth, it shall be called New Xaculon.'
```

## Nested Objects
An object might have another object as a property which is turn could have a property that's an array of even more objects.

```js
let spaceship = {
  passengers: null,
  telescope: {
    yearBuilt: 2018,
    model: "91031-XLT",
    focalLength: 2032 
  },
  crew: {
    captain: { 
      name: 'Sandra', 
      degree: 'Computer Engineering', 
      encourageTeam() { console.log('We got this!') },
     'favorite foods': ['cookies', 'cakes', 'candy', 'spinach'] }
  },
  engine: {
    model: "Nimbus2000"
  },
  nanoelectronics: {
    computer: {
      terabytes: 100,
      monitors: "HD"
    },
    'back-up': {
      battery: "Lithium",
      terabytes: 50
    }
  }
}; 

const capFave = spaceship.crew.captain['favorite foods'][0];

spaceship.passengers = [{name: 'David'}, {name: 'Pedro'}];

const firstPassenger = spaceship.passengers[0];

console.log(firstPassenger); // Prints { name: 'David' }
```

## Pass By Reference
Objects are *passed by reference.* This means when we pass a variable assigned to an object into a function as an argument, the computer interprets the parameter name as pointing to the space in memory holding that object.

```js
const spaceship = {
  homePlanet : 'Earth',
  color : 'silver'
};

let paintIt = obj => {
  obj.color =  'glorious gold'
};

paintIt(spaceship);
spaceship.color // Returns 'glorious gold'
```

However, reassignment of the `spaceship` variable wouldn't work in the same way:

```js
let spaceship = {
  homePlanet : 'Earth',
  color : 'red'
};
let tryReassignment = obj => {
  obj = {
    identified : false, 
    'transport type' : 'flying'
  }
  console.log(obj) // Prints {'identified': false, 'transport type': 'flying'}

};
tryReassignment(spaceship) // The attempt at reassignment does not work.
spaceship // Still returns {homePlanet : 'Earth', color : 'red'};

spaceship = {
  identified : false, 
  'transport type': 'flying'
}; // Regular reassignment still works.
```
+ When we passed `spaceship` into that function, `obj` became a reference to the memory location of the `spaceship` object, but *not* to the spaceship variable. This is because the `obj` parameter of the `tryReassignment()` function is a variable in its own right. The body of `tryReassignment()` has no knowledge of the `spaceship` variable at all.
