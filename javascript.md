# JavaScript 101

This page was written following [CodeCademy Introduction to JavaScript](https://www.codecademy.com/learn/introduction-to-javascript/) and Le Wagon's additional resources.

## The basics

[JavaScript reference (MDN documentation)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference)

Primitive data types: Number, String, Boolean, Null, Undefined, Symbol
Values that evaluate to `false`: `0`, `""`, `null`, `undefined`, `NaN`

### Some syntax

``` javascript
// one line comment
/* multi
line
comment */
console.log('logging stuff');

let maVariable; // creates a variable named maVariable
const maConstante; // creates a constant names maConstante

let myName = 'Pil0u';
console.log(`I, ${myName}, am able to interpolate.`); // notice the `
typeof myName; // string

let myArray = ['this', 'is', 'an', 'array'];
// Variables declared with the const keyword cannot be reassigned. However, elements in an array declared with const remain mutable. Meaning that we can change the contents of a const array, but cannot reassign a new array or a different value.
myArray.push('item1', 'item2'); // appends
myArray.pop(); // removes from the end INPLACE
// .length, .join(), .slice(), .splice(), .shift() (removes first item), .unshift() (appends from start), .concat(), indexOf()

let objectLiteral = {
	coco: 'rico',
	'Le Bon': 'La Brute'
};

objectLiteral.coco; // => 'rico'
objectLiteral['Le Bon']; // => 'La Brute'
delete objectLiteral.coco;

```

### Conditions 

``` javascript
if (condition) {
	// do stuff
} else if (condition) {
	// do other stuff
} else {
	// do other stuff
}

// use === for equality and !== for inequality comparisons
// use && for the logical AND and || for the logical OR

let username = myName || 'Anonymous'

username ? /* if yes */ : /* if not */

switch (season) {
	case 'summer':
		// do stuff;
		break;
	case 'winter':
		// do stuff;
		break;
	default:
		// do stuff;
		break;
}
```

### Functions

``` javascript
function myFunction(parameter = default_value) {
	// do stuff
	return // stuff;
}

myFunction(); // to call it

// Anonymous functions
const variable = function(parameter) {
	// do stuff
}
variable(argument);

// Arrow functions syntax
const rectangleArea = (width, height) => {
  let area = width * height;
  return area;
}

const functionName = () => {} // no parameter
const functionName = paramOne => {} // one parameter, no brackets needed
const functionName = (paramOne, paramTwo) => {} // 2+ parameters, brackets needed
const sumNumbers = number => number * 2; // one-line function, neithor braces nor return needed

// Higher order functions (higher order)
```

[A good explanation on the `this` and Arrow Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions) (they should not be used for method definition)

### Loops

``` javascript
// for loop
for (let i = 0; i < myArray.length; i++){
  console.log(myArray[i]);
}

// while loop
let counterTwo = 1;
while (counterTwo < 4) {
  console.log(counterTwo);
  counterTwo++;
}

// do while loop
const cupsOfSugarNeeded = 14;
let cupsAdded = 0;
do {
  cupsAdded++;
} while (cupsAdded < cupsOfSugarNeeded);

// for in loop on objects NOT arrays
for (let crew in spaceship.crew) {
	console.log(`${spaceship.crew[crew].name}: ${spaceship.crew[crew].degree}`);
}
```

### Iterators

``` javascript
const fruits = ['coco', 'rico']

fruits.forEach(fruit => {
	// do stuff
})

const firstLetters = fruits.map(fruit => {
	return fruit[0];
})

const startsWithC = fruits.filter(fruit => {
	return fruit[0] === 'c';
})

// .findIndex, .reduce (???), .some, .every
```

[List of Arrays iterators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array#Iteration_methods)

### OOP

Use a `_` in front of an object key to show it is private (convention).

``` javascript
const myObject = {
	get myGetter() {},
	set mySetter(param) {}
}

// Factory functions return objects
const robotFactory = (model, energyLevel) => {
	return {
		model: model,
		name: name
	}
};
// The destructured equivalent:
const robotFactory = (model, energyLevel) => {
	return {
		model,
		name
	}
};

// Destructured assignment
const r2d2 = {
	funny: true,
	wheels: {
		size: 34,
		type: 'round'
	}
};

const size = r2d2.wheels.size; 
// is equivalent to
const { size } = r2d2.wheels;

const robotKeys = Object.keys(r2d2);
```


### Utilities

``` javascript
Number.parseInt('42', 10); // => 42
()


```