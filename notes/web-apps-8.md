# 8 - JavaScript Arrays

## Overview

JavaScript arrays are "List-like" objects that are used to store information sequentially. 
Unlike primitive (Int, Float etc) arrays in languages like C, JavaScript arrays are NOT constrained to holding only one *type* of value, and can hold multiple types of data in the same array.

## Contents
<!--- Local Navigation --->
I. [Array Operations](#section1)

II. [Iterating over Arrays](#section2)

III. [Other "Array-like" objects in JavaScript](#section3)

IV. [Nota bene](#section4)

V. [Review Questions](#section5)'

<hr><hr>

## I. <a id="section1">Array Operations

### A. Create an Array
```
// An array of strings
let colors = ["red","green","blue"];
console.log(`colors.length = ${colors.length}`); // 3

// an array of numbers
let numbers = [7.9, 5.9, 100.3];

// mixed typed
let collection = ["Jaberwocky", 42, 98.6, false, Date(), Math.sin, null];
```

### B. Access an Array item

```
let first = colors[0]; // "red"
let last = colors[colors.length - 1]; // "blue"
```

### C. Add to the end of an Array

```
colors.push("purple");
```

### D. Remove from the end of an Array

```
last = colors.pop(); // remove "purple" from the end
```


### E. Remove from the front of an Array

```
first = colors.shift(); // remove "red" from beginning
```


### F. Add to the front of an Array

```
colors.unshift("red"); // add "red" back to the front
```

### G. Find the index of an item in the Array

```
let pos = colors.indexOf("green");
```

### H. Remove 1 or more items by index position

```
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

```
let fruits = ["apples","oranges","bananas"];
position = 0;
let numberToCopy = 2;
let copiedItems = fruits.slice(position,numberToCopy);

console.log(fruits); // ["apples","oranges","bananas"]
console.log(copiedItems); // ["apples","oranges"]
```

### J. Copy the whole array

Note: a shallow copy only copies object references

```
let shallowCopy = fruits.slice();
console.log(shallowCopy); // ["apples","oranges","bananas"]

let car = {make:"Ford"};
let cars = [car];
let carsCopy = cars.slice();
console.log(car == cars[0] && cars[0] == carsCopy[0]); // true, all the same car
```

### K. Sample code for this section
#### array-operations.html

```
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

```
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

```
for (let color of colors){
	console.log(color);
	// we can also use break and continue
}
```

### C. `Array.forEach()`

`.forEach()` is a method of Array - we pass it a function that will be called on every member of the array.
One disadvantage of `.forEach()` is that you can not break out of the loop early.

```
colors.forEach(function(item, index, array) {
  console.log(item, index);
});
```

### D. `Array.map()`

The `map()` method creates a new array that contains the results of calling the passed in function on every element in the original array.

```
let numbers = [1,2,3,4];
let doubleIt = function(num){return num * 2};
//let doubleIt = num => num * 2; // same thing as an arrow function
let newArray = numbers.map(doubleIt); // [2,4,6,8]

```

### E. `Array.filter()`
The `filter()` method creates a new array with all elements that pass the test (i.e return `true`) implemented by the provided function.

```
let evenOnly = function(num){return num % 2 == 0};
//let evenOnly = num => num % 2 == 0; // same thing as an ES6 arrow function
let filteredArray = numbers.filter(evenOnly); // [2,4]
```

### F. Sample code for this section
#### array-iteration.html

```
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

NodeLists are NOT arrays. Although they have a `.length` property and can use `for...of` and `.forEach()`, they CAN not use other array methods like `.filter()` or `.map()`.

```
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

```
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

// NodeList does not have the .filter() method
let filteredArray = allNodes.filter(node => node.tagName == "BODY"); //FAIL!

debugger;
</script>
</body>
</html>
```
## IV. <a id="section4">Nota bene
Nothing for now.

## V. <a id="section5">Review Questions
1. True or False. JavaScript Arrays may hold only a single *type* of value.
1. Which array operation adds an item to the *end* of an array?
1. Which array method can be used to *remove* items from an array?
1. Which array method can be used to *copy* items to a new array?
1. Describe 3 ways to loop through a JavaScript Array.
1. Does `Array.filter()` modify the old array (the one it is called on), or create a new array?
1. What is the type of the object that is returned by `document.querySelectorAll()`?

<hr>

**[Previous Section <- JavaScript Object Literals (part 7)](web-apps-7.md)**

**[Next Section -> Web Storage (part 9)](web-apps-9.md)**
