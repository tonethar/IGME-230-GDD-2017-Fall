# 8 - JavaScript Arrays

## Overview

JavaScript arrays are "List-like" objects that are used to store information sequentially. 
Unlike primitive arrays (Int, Float etc) in languages like C, JavaScript arrays are NOT constrained to holding only one *type* of value, and can hold multiple types of data in the same array.

## Contents
<!--- Local Navigation --->
I. [Array Operations](#section1)

II. [Iterating over Arrays](#section2)

III. [Other "Array-like" objects in JavaScript](#section3)

IV. [Nota bene](#section4)

V. [Review Questions](#section5)

VI. [Review Exercise](#section6)

<hr><hr>

## I. <a id="section1">Array Operations

### A. Create an Array
```javascript
// empty arrays
let emptyArray1 = []; 			// array literal syntax
let emptyArray2 = new Array(); 		// this second method is not commonly used

// an array of strings
let colors = ["red","green","blue"];
console.log(`colors.length = ${colors.length}`); // 3

// an array of numbers
let numbers = [7.9, 5.9, 100.3];

// mixed types in the same Array
let collection = ["Jaberwocky", 42, 98.6, false, Date(), Math.sin, null];
```

#### 2-Dimensional Arrays
This example of an 8x8 2-D array is from: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array

The following creates a chess board as a two dimensional array of strings. The first move is made by copying the 'p' in (6,4) to (4,4). The old position (6,4) is made blank.

```javascript
var board = [ 
  ['R','N','B','Q','K','B','N','R'],
  ['P','P','P','P','P','P','P','P'],
  [' ',' ',' ',' ',' ',' ',' ',' '],
  [' ',' ',' ',' ',' ',' ',' ',' '],
  [' ',' ',' ',' ',' ',' ',' ',' '],
  [' ',' ',' ',' ',' ',' ',' ',' '],
  ['p','p','p','p','p','p','p','p'],
  ['r','n','b','q','k','b','n','r'] ];

// Move King's Pawn forward 2
board[4][4] = board[6][4];
board[6][4] = ' ';
```

### B. Access an Array item

```javascript
let first = colors[0]; // "red"
let last = colors[colors.length - 1]; // "blue"
```

### C. Add to the end of an Array

```javascript
colors.push("purple");
```

### D. Remove from the end of an Array

```javascript
last = colors.pop(); // remove "purple" from the end
```


### E. Remove from the front of an Array

```javascript
first = colors.shift(); // remove "red" from beginning
```


### F. Add to the front of an Array

```javascript
colors.unshift("red"); // add "red" back to the front
```

### G. Find the index of an item in the Array

```javascript
let pos = colors.indexOf("green");
```

### H. Remove 1 or more items by index position

```javascript
// remove 1 item
position = 2;
let numberToRemove = 1;
let removedArray1 = colors.splice(position, numberToRemove); // ["blue"]

// remove more than 1
position = 0;
numberToRemove = 2;
let removedArray2 = colors.splice(position, numberToRemove);  // ["red","green"]

console.log(`colors.length = ${colors.length}`); // 0
```
                                    

### I. Copy an item from an index position

```javascript
let fruits = ["apples","oranges","bananas"];
position = 0;
let numberToCopy = 2;
let copiedItems = fruits.slice(position,numberToCopy);

console.log(fruits); // ["apples","oranges","bananas"]
console.log(copiedItems); // ["apples","oranges"]
```

### J. Copy the whole array

Note: a shallow copy only copies object references

```javascript
let shallowCopy = fruits.slice();
console.log(shallowCopy); // ["apples","oranges","bananas"]

let car = {make:"Ford"};
let cars = [car];
let carsCopy = cars.slice();
console.log(car == cars[0] && cars[0] == carsCopy[0]); // true, all the same car
```

### K. Sample code for this section
#### array-operations.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title>Array Operations</title>
</head>
<body>

<script>
// A.
// An array of strings
let colors = ["red","green","blue"];
console.log(`colors.length = ${colors.length}`); // 3

// an array of numbers
let numbers = [7.9, 5.9, 100.3];

// mixed typed
let collection = ["Jaberwocky", 42, 98.6, false, Date(), Math.sin, null];

// B.
let first = colors[0]; // "red"
let last = colors[colors.length - 1]; // "blue"

// C.
colors.push("purple");

// D.
last = colors.pop(); // remove "purple" from the end

// E.
first = colors.shift(); // remove "red" from beginning

// F.
colors.unshift("red"); // add "red" back to the front

// G.
let position = colors.indexOf("green"); // 1

// H.
// remove 1 item
position = 2;
let numberToRemove = 1;
let removedArray1 = colors.splice(position, numberToRemove); // ["blue"]

// remove more than 1
position = 0;
numberToRemove = 2;
let removedArray2 = colors.splice(position, numberToRemove); // ["red","green"]

console.log(`colors.length = ${colors.length}`); // 0

// I
let fruits = ["apples","oranges","bananas"];
position = 0;
let numberToCopy = 2;
let copiedItems = fruits.slice(position,numberToCopy);
console.log(fruits); // ["apples","oranges","bananas"]
console.log(copiedItems); // ["apples","oranges"]

// J
let shallowCopy = fruits.slice();
console.log(shallowCopy); // ["apples","oranges","bananas"]

let car = {make:"Ford"};
let cars = [car];
let carsCopy = cars.slice();
console.log(car == cars[0] && cars[0] == carsCopy[0]); // true, all the same car

debugger;

</script>
</body>
</html>
```

## II. <a id="section2">Iterating over Arrays

### A. `for` loop

```javascript
for (let i=0; i<colors.length; i++){
	console.log(colors[i]);
}

for (let i=0; i<colors.length; i++){
	console.log(colors[i]);
	if (colors[i] == "red") break; // stop after "red"
}

for (let i=0; i<colors.length; i++){
	if (colors[i] == "red") continue; // skip "red"
	console.log(colors[i]);
}
```

### B. `for...of` loop

```javascript
for (let color of colors){
	console.log(color);
	// we can also use break and continue
}
```

### C. `Array.forEach()`

`.forEach()` is a method of Array - we pass it a function that will be called on every member of the array.
One disadvantage of `.forEach()` is that you can not break out of the loop early.

```javascript
colors.forEach(function(item, index, array) {
  console.log(item, index);
});
```

### D. `Array.map()`

The `map()` method creates a new array that contains the results of calling the passed in function on every element in the original array.

```javascript
let numbers = [1,2,3,4];
let doubleIt = function(num){return num * 2};
//let doubleIt = num => num * 2; // same thing as an arrow function
let newArray = numbers.map(doubleIt); // [2,4,6,8]

```

### E. `Array.filter()`
The `filter()` method creates a new array with all elements that pass the test (i.e return `true`) implemented by the provided function.

```javascript
let evenOnly = function(num){return num % 2 == 0};
//let evenOnly = num => num % 2 == 0; // same thing as an ES6 arrow function
let filteredArray = numbers.filter(evenOnly); // [2,4]
```

### F. Sample code for this section
#### array-iteration.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title>Array Iteration</title>
</head>
<body>

<script>
let colors = ["red","green","blue"];

// A
for (let i=0; i<colors.length; i++){
	console.log(colors[i]);
}

for (let i=0; i<colors.length; i++){
	console.log(colors[i]);
	if (colors[i] == "red") break; // stop after "red"
}

for (let i=0; i<colors.length; i++){
	if (colors[i] == "red") continue; // skip "red"
	console.log(colors[i]);
}

// B
for (let color of colors){
	console.log(color);
	// we can also use break and continue
}


// C
colors.forEach(function(item, index, array) {
  console.log(item, index);
});

// D
let numbers = [1,2,3,4];
let doubleIt = function(num){return num * 2};
//let doubleIt = num => num * 2; // same thing as an ES6 arrow function
let newArray = numbers.map(doubleIt); // [2,4,6,8]

// E
let evenOnly = function(num){return num % 2 == 0};
//let evenOnly = num => num % 2 == 0; // same thing as an ES6 arrow function
let filteredArray = numbers.filter(evenOnly); // [2,4]

debugger;
</script>
</body>
</html>

```


## III. <a id="section3">Other "Array-like" objects in JavaScript
### A. `NodeList`

When we use `document.querySelectorAll()`, we get back a `NodeList`.

- https://developer.mozilla.org/en-US/docs/Web/API/NodeList

NodeLists are NOT arrays. Although they have a `.length` property and can use `for...of` and `.forEach()`, they CANNOT use other array methods like `.filter()` or `.map()`.

```javascript
let allNodes = document.querySelectorAll("*"); // returns a NodeList object

for (let i=0;i<allNodes.length;i++){
	console.log(allNodes[i]); // works fine
}

for (let node of allNodes){
	console.log(node); // works fine
}

allNodes.forEach(function(item, index, array) {
  console.log(item, index); // works fine on newer browsers
});

// NodeList does not have the .filter() method
let filteredArray = allNodes.filter(node => node.tagName == "BODY"); //FAIL!
```

### B. Typed Arrays

Typed arrays are fixed size arrays that hold only a single primitive tyope, such as a `UInt8` or a `Float64`. We probably won't use them in this class, and you can read about them here: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Typed_arrays


### C. Sample code for this section
#### array-like-objects.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title>Array-like Objects</title>
</head>
<body>

<script>
// A
let allNodes = document.querySelectorAll("*"); // returns a NodeList object

for (let i=0;i<allNodes.length;i++){
	console.log(allNodes[i]); // works fine
}

for (let node of allNodes){
	console.log(node); // works fine
}

allNodes.forEach(function(item, index, array) {
  console.log(item, index); // works fine on newer browsers
});

// NodeList does NOT have the .filter() method!
let filteredArray = allNodes.filter(node => node.tagName == "BODY"); //FAIL!

debugger;
</script>
</body>
</html>
```
## IV. <a id="section4">Nota bene

What if we have a `NodeList`, but need access to `Array` methods?  Easy, just move the contents of the `NodeList` into a new `Array`!

```javascript

// Here are 4 ways to convert a NodeList to an array (there are others):

// 1 - a for loop
let array1 = [];
for(let i = 0, node; node = allNodes[i]; ++i) array1.push(node);

// 2 - call the slice() method on the NodeList 
let array2 = Array.prototype.slice.call(allNodes);

// 3 - .from() is a new Array method for ES6
let array3 = Array.from(allNodes); 	

// 4 - ES6 spread operator
let array4 = [...allNodes]; 		
```

## V. <a id="section5">Review Questions
1. True or False. JavaScript Arrays may hold only a single *type* of value.
1. Which array operation adds an item to the *end* of an array?
1. Which array method can be used to *remove* items from an array?
1. Which array method can be used to *copy* items to a new array?
1. Describe 3 ways to loop through a JavaScript Array.
1. Does `Array.filter()` modify the old array (the one it is called on), or create a new array?
1. What is the type of the object that is returned by `document.querySelectorAll()`?

## VI. <a id="section6">Review Exercise

See the HTML comments in the starter code below for what you have to do - name this **web-apps-8-HW.html**

### web-apps-8-HW.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title>web-apps-8-HW</title>
</head>
<body>
<script>
let cars = [
	{make:"Toyota",	year:2015},
	{make:"Jeep",	year:1946},
	{make:"Ford",	year:2017},
	{make:"Tesla",	year:2018},
	{make:"Fiat",	year:1982},
	{make:"Dodge",	year:1970},
	{make:"Chevy",	year:1957},
];

// For this HW you will use Array.filter(), Array.sort(), and Array.map() on
// the cars array above.

/*
 1 - Create a new array named 'classicCars' that contains only those cars with a
 .year of 1970 or earlier. Use Array.filter() on the cars array:
 https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter
*/


/*
 2 - Create a new array named 'sortedByYear' that contains the contents of the
 car array, sorted by .year, ascending (oldest to most recent)
 Use Array.sort() on the cars array - and read about writing a comparison function here:
 https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort
 
*/


/*
 3 - Create a new array named 'newerYearsOnly' that contains only the .year property 
 (not the entire car object) of those cars that are .year 2010 or newer. 
 Use Array.map() on the cars array:
 https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map
 
 This will give you a few undefined values. Use Array.filter() to get rid of these 
 undefined values so that newerYearsOnly contains only years (Numbers)
 
 Hint: you could use Number.isInteger() or the typeof operator:
 https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/isInteger
 https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/typeof
 
 You could do this additional filter on a separate filter on the different lines,
 or as a "one-liner" by chaining the method calls.
*/

debugger;
</script>
</body>
</html>
```

**Which looks like this in the debugger:**

![Web Page](_images/arrays-1.jpg)

<hr>

- **Important:** If you have not yet done the [Pixel Artist](HW-pixel-artist.md) homework, go check it out. See the mycourses dropbox for the actual due date.
- Also be sure to check the [Life](HW-life.md) and [Adventure!](HW-adventure.md) demos.

<hr>

**[Previous Chapter <- JavaScript Object Literals (chapter 7)](web-apps-7.md)**

**[Next Chapter -> Web Storage (chapter 9)](web-apps-9.md)**
