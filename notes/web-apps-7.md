# 7 - JavaScript Object Literals

##  Overview
JavaScript is an *Object-Oriented* language, but traditional classes have not been supported until recently (ES6). 

Today we will look at doing object-oriented programming *without* using classes, by utilizing the **JavaScript Object Literal**, and see how powerful and flexible it is.

If you want to create an object in most computer languages, you first need to create a *template* (aka a *class*) that describes what the instance variables and methods of the class are. You then use the class to create *instances* of each object. In most languages it is impossible to add new properties and methods to an existing class or object - to do so you will have to create a new class, and then sub-class the old class, and then create a new instance.

Creating objects in JavaScript can be much easier, you can skip step #1 (creating a template), and move directly to step #2 (creating an instance).

## Contents
<!--- Local Navigation --->
I. [What is a *literal value*?](#section1)

II. [Creating Object Literals](#section2)

III. [Iterating over object properties](#section3)

IV. [Adding behavior to our objects](#section4)

V. [Creating "object factories"](#section5)

VI. [ES6 Object Literal syntax](#section6)

VII. [Value Types & Reference Types](#section7)

VIII. [Another look at `const`](#section8)

VIII. [Nota bene](#section9)

IX. [Review Questions](#section10)

X. [Review Exercise](#section11)

<hr><hr>

## I. <a id="section1">What is a *literal value*?
In programming, a literal value is *a notation for representing a fixed value in source code*, or *a value written exactly as it's meant to be interpreted*.

Here are some literals in the JavaScript Language:

```javascript
let a = "abcd";                         // a String literal 
let b = 1234;                           // a Number literal 
let c = true;                           // a Boolean literal 
let e = arg => return arg * 2;          // a Function literal (ES6 arrow style)
let d = [];                             // an Array literal 
let f = {};                             // an Object literal!
```

NOT literals:

```javascript
let g = Array();
let h = Date();
let i = Math.random();
let h = b * 10; // 10 is a literal but 'b' is not
```


## II. <a id="section2">Creating Object Literals
Here we are going to create an object literal named `car1`, and attach a few properties to it. The way we do this is to specify a *key* and a *value* (in this form - `key:value`)

### objects-1.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <title>Objects-1</title>
</head>
<body>
<script>
"use strict";
// 1 - Create an object literal with properties
let car1 = {
  make: "Ford",
  model: "Pinto",
  cylinders: 4
};

// 2 - Add properties to existing objects
car1.color = "Red"; // add properties to objects with dot syntax
car1["year"] = 1972; // or with brackets

// 3 -  Delete properties from an object with the delete operator
delete car1["color"];
delete car1.year;

// 4 - access property values with dot syntax, or square brackets
console.log(car1.make); // Ford
console.log(car1["model"]); // Pinto

</script>
</body>
</html>
```

### A. Explanation
- note that we can easily add a property to an existing object. This can lead to odd errors.
Imagine this:

```javascript
// 1- below we misspell cylinders, so 'a' is now 'undefined'
let a = car1.clyinders; 

// 2- below we misspelled .cylinders, and created a new property on car1 named "clyinders"
car1.clyinders = 10; 

// 3- Object.seal() to the rescue!
// Object.seal() will ensure we can't add new properties to an object
Object.seal(car1);
car1.newproperty = 1000; // will fail quietly or throw an error, depends on browser
console.log(car1.newproperty); // undefined
```

- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/seal
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/freeze

**`Object.freeze()` allows us to seal the object (on new properties), and then make the existing properties *immutable***

Attempting to change a property on a "frozen" object results in an error (in strict mode) or a no-op otherwise.
```javascript
"use strict";
let car1 = {
  make: "Ford",
  model: "Pinto",
  cylinders: 4
};

Object.freeze(car1);
car1.make = "Chevy"; // ERROR - "Uncaught TypeError: Cannot assign to read only property 'make' of object"
```
**Note that `Object.freeze()` only freezes top-level properties - it will not freeze the properties of nested objects.**

## III. <a id="section3">Iterating over object properties
The `for...in` loop is commonly used to iterate over object properties.

Add the following to **objects-1.html**:

```javascript
// 5 - iterate over keys of object with for...in
for (key in car1){
  console.log(`key=${key}`); // make,model,cylinders
}

// 6 - here we are using the keys to get the values
for (key in car1){
  console.log(car1[key]); // Ford,Pinto,4
}

// 7 - Object.keys() is a recent addition, it returns an array of the keys of an object
console.log(Object.keys(car1)); // ["make", "model", "cylinders"]


// 8 - the fancy ES6 way to iterate over object properties
Object.keys(car1).map(key => console.log(`key=${key}  value=${car1[key]}`));

/*
key=make  value=Ford
key=model  value=Pinto
key=cylinders  value=4
*/

```

## IV. <a id="section4">Adding behavior to our objects

Objects usually have *state* (properties or instance variables) AND *behavior* (methods).

Can we add behavior to our JavaScript object literals? You betcha!

In JavaScript objects, *methods are properties whose values are functions*.

### objects-2.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title>Objects-2</title>
</head>
<body>
<script>
"use strict";
// 1 - Create an object literal with properties AND methods
let car1 = {
	make: "Ford",
	model: "Pinto",
	cylinders: 4,
	maxSpeed: 100,
	speed: 10,
	speedUp: function(howMuch){
// 2- we need to use "this" whenever we refer to a property of the current object
		this.speed += howMuch; 
		if(this.speed > this.maxSpeed){
			this.speed = maxSpeed;
		}
	},
	stop: function(){
		this.speed = 0;
	}
};

console.log(car1.speed); // 10
car1.speedUp(50); 		// car1.speed is now 60
car1.stop(); 			// car1.speed is now 0


</script>
</body>
</html>
```

### A. Explanation
- Here we are adding functions as the values of properties - which makes them *methods* of the object they are attached to.
- Note that we have to use the `this` keyword when we refer to a property of the current object. 

## V. <a id="section5">Creating "object factories"
What if we had a game that needed to have 50 cars driving around? Creating 50 object literals - `car1 = {...} ,car2 = {...}, car3 = {...}` would be both tedious and error prone.
Instead, we can write a function to create these cars for us.

### objects-3.html
```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title>Objects-3</title>
</head>
<body>
<script>
"use strict";
// 1 - create two functions that we will later use as a "method"
let speedUp = function(howMuch){
		this.speed += howMuch; 
		if(this.speed > this.maxSpeed){
			this.speed = maxSpeed;
		}
}

let stop = function(){ this.speed = 0; }


// 2 - Here is our "factory" function
function makeCar(make,model,cylinders=4,speed=10, maxSpeed=100){
	let car = {
		make: make,
		model: model,
		cylinders: cylinders,
		speed: speed,
		maxSpeed: maxSpeed,
		speedUp: speedUp,
		stop: stop
	};
	
	// 3 - seal it so that no new properties may be added
	Object.seal(car);
	return car;
}

// 4 - make some cars and log them to the console
let car1 = makeCar("Toyota","Corolla");
console.log(car1);

let car2 = makeCar("Toyota","Camry",6);
car2.stop();
console.log(car2);

let car3 = makeCar("Toyota","Tundra",8,50,200);
car3.speedUp(100);
console.log(car3);


// 5 - add the cars to an array
console.log("----- now loop through cars -----");
let cars = [car1,car2,car3];
for (car of cars){
   car.speedUp(10);
   console.log(car);	
}
</script>
</body>
</html>
```

### A. Explanation
- In #1 above, we create two functions that we will later add to our cars as methods. We are creating these functions *outside* of our factory function because we want the cars to *share* a single copy of each function, rather than for each instance of car to have their own copy of the function. This will reduce the overall memory footprint of our car instances - which is a good thing!
- In #2 above we declare `makeCar()` and give it 5 parameters, 3 of which are optional in that we have provided default values.
- In #3 we use `Object.seal()` to prevent new properties from being added to an object.
- In #4 and #5 we test our factory factory methods, and see how we can loop through an array of cars and call methods on them.

<hr>

### ** *Try This!* **
- In *object-3.html*, add a `isJunked` parameter to `makeCar()`, and give it a default value of `false`.
- Make sure that the `car` literal is assigned the value of `isJunked` as a property.

<hr>

## VI. <a id="section6">ES6 Object Literal syntax
In ES6, the Object literal syntax gives the developer more concise ways to declare properties and values with *property value shortcuts*, and a more compact way of defining object methods. See below:

### objects-4.html
```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title>Objects-4</title>
</head>
<body>
<script>
"use strict";
// NEW ES6 Object Literal Feature

// 1- property value "shortcuts"

// 1A - old way
function makeCar1(make,model,cylinders){
	return {
		make: make,
		model: model,
		cylinders: cylinders
	};
}

// 1B - new ES6 way works as long as the property name and value use the same identifier
function makeCar2(make,model,cylinders){
	return {
		make,
		model,
		cylinders
	};
}

console.log(makeCar1("Subaru","Brat",4));
console.log(makeCar2("Plymouth","Champ",4));


// 2 - new and more concise way to specify object methods

// 2A - old way
let car1 = {
	speed: 0,
	speedUp: function(){
		this.speed ++;
	},
	stop: function(){
		this.speed = 0;
	}
};


// 2B - new ES6 way
let car2 = {
	speed: 0,
	speedUp(){
		this.speed ++;
	},
	stop(){
		this.speed = 0;
	}
};
</script>
</body>
</html>
```

## VII. <a id="section7">Value types & Reference types

- Javascript has 5 data types that are passed by *value*: Boolean, Number, String, null, and undefined. We could also call these *primitive* types.
- Javascript has 3 data types that are passed by *reference*: Array, Function, and Object. In actuality, all of these are Objects. DOM Elements are Objects and are thus also *reference* types.

### A. Value types
How are value types like String and Number copied between variables? Here is an example:

```javascript
let a = 100;
let b = a;
a = 50;

console.log(a); // 50
console.log(b); // 100
```

- The line `let b = a;` copies the value of 100 into the `b` variable. When we later change `a` to `50`, we are only effecting `a`, not `b`.
- The above behavior is how value types work: variable assignment *copies* the actual value from the old variable to the new variable, and later changes to one variable's value have no effect upon the other variable's value.

### B. Reference types

How are reference types "copied" between variables? Here is an example:

```javascript
let car1 = {make:"Toyota"};
let car2 = car1; // car1 and car2 are now pointing at the same object!
car1.make = "Jeep"; // changes made to car1 effect both variables

console.log(car1.make); // Jeep
console.log(car2.make); // Jeep

let car3 = car1; // now 3 variables are pointing at the same object!
car3.make = "Yugo";

console.log(car1.make); // Yugo
console.log(car2.make); // Yugo
console.log(car3.make); // Yugo
```
- Reference types (Objects, Arrays Functions, Elements, ...) are different in that variable assignment *points* at an independent object existing in memory, and assigning another variable to point at the first variable copies the *reference to the object*, not the value itself. Changes made to the referenced object are seen by all of the variables that point at that object.

## VIII. <a id="section8">Another look at `const`
Now that we have had a chance to look at Objects, let's look at the description of [`const`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const) from the Mozilla site: 

"The `const` declaration creates a read-only reference to a value. It does not mean the value it holds is immutable, just that the variable identifier cannot be reassigned. For instance, in the case where the content is an object, this means the object's contents (e.g., its parameters) can be altered."

Let's look at an example:
	
```javascript
// A. For primitives, const means we CAN NOT change the value
const PI = 3.14;
const FIRST_PRESIDENT  = "Washington";
const skyIsBlue = true;

PI = 3.1416; 				// error
FIRST_PRESIDENT = "Trump"; 		// error
skyIsBlue = false; 			// error


// B. But for Objects, const means we CAN change the values of the object properties,
// or the contents of the array
const car = {make:"Toyota"};
const colors = ["red","green"];

car.model = "Tercel"; 			// legal
colors.push("blue");			// legal


// C. but CAN NOT change the reference
car = {make: "Jeep"}; 			// error
colors = ["magenta","teal"]; 		// error


// D. which gives (after you comment out the error lines)
console.log(car); 			// {make:"Toyota", model: "Tercel"}
console.log(colors);			// ["red","green","blue"]

```

**So with `const`, what is immutable is the *binding* of the variable to the value, and with `const` the compiler guarantees that a *re-binding* will not occur.**

## IX. <a id="section9">Nota bene
For more information on object literals, head here: http://exploringjs.com/es6/ch_oop-besides-classes.html

## X. <a id="section10">Review Questions
1. In programming, what is a *literal* value?
1. How do you iterate over the keys and values of an object?
1. What is the difference between `for...in` and `for...of`? (You don't want to get these 2 mixed up!)
1. List 3 JavaScript *value* types.
1. List 3 JavaScript *reference* types.
1. What does `Object.seal()` do?
1. What does `Object.freeze()` do?
1. What is wrong with the following code?
```javascript
var ship={
  x: 0,
  y: 0,
  speed: 10,
    move: function(){
      x += speed;
      y += speed;
    }
}
```
9. See the code below. What will be logged for the values of `x` and `y`? (Please try to figure this out on your own first, before running it in the browser to verify your answer.)
```javascript
  let x = "1";
  let y = x;
  x = "2";
  console.log(x);
  console.log(y);
```
10. See the code below. What will be logged for the values of `x` and `y`? (Please try to figure this out on your own first, before running it in the browser to verify your answer.)
```javascript
  let x = [1,2,3];
  let y = x;
  x.push(4);
  y.push(5);
  console.log(x);
  console.log(y);
```
11. See the code below. What will be logged for the values of `x`, `y` and `z`? (Please try to figure this out on your own first, before running it in the browser to verify your answer.) If any errors occur, please assume that the JavaScript interpreter will move on to the next line of code and continue to run.
```javascript
  const x = {};
  const y = 1;
  const z = {};
  x.name = "fred";
  y++;
  z = {"name":"mary"};
  console.log(x);
  console.log(y);
  console.log(z);
```

## XI. <a id="section11">Review Exercise
Easy - just head back to the exercise for [4 - More Web Browser DOM Methods](web-apps-4.md) - make a copy of the file and name it **web-apps-7-HW.html**, and do the challenge:

```javascript
 // Can you figure out how to pull the key and value from the "links" object literal?
 // and put them in list with clickable links?
let links = {
		"RIT": "http://www.rit.edu",
		"RWAG" : "https://www.facebook.com/RWAGclub",
		"New Media Club" : "http://newmediaclub.cias.rit.edu"
	}
```

<hr>

- **Important:** If you have not yet done the [Magnetic Poetry](HW-magnetic-poetry.md) homework, go check it out. See the mycourses dropbox for the actual due date.

<hr>

**[Previous Chapter <- JavaScript Events (chapter 6)](web-apps-6.md)**

**[Next Chapter -> JavaScript Arrays (chapter 8)](web-apps-8.md)**
