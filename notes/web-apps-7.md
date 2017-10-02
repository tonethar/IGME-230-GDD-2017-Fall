# 7 - JavaScript Object Literals

##  Overview

JavaScript is an *Object-Oriented* language, but traditional classes have not been supported until ES6. Today we will look at the powerful **JavaScript Object Literal**, and see how powerful and flexible it is.

## I. What is a *literal value*?
In programming, a literal value is *a notation for representing a fixed value in source code*, or *a value written exactly as it's meant to be interpreted*.

Here are some literals in the JavaScript Language:

```
let a = "abcd";                         // a literal String
let b = 1234;                           // a literal Number
let c = true;                           // a literal Boolean
let d = [];                             // a literal Array
let e = arg => return arg * 2;          // a literal Function
let f = {};                             // an object literal!
```

NOT literals:

```
let g = Array();
let h = b * 10;
```


## II. Creating Object Literals
Here we are going to create an object literal named `car1`, and attach a few properties to it. The way we do this is to specify a *key* and a *value* (in this form - `key:value`)

### objects-1.html

```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <title>Objects-1</title>
</head>
<body>
<script>

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

```
// 1- below we misspell cylinders, so 'a' is now 'undefined'
let a = car1.clyinders; 

// 2- below we misspelled .cylinders, and created a new property
car1.clyinders = 10; 

// 3- Object.seal() to the rescue!
// Object.seal() will ensure we can't add new properties to an object
Object.seal(car1);
car1.newproperty = 1000; // might fail quietly or throw an error
console.log(car1.newproperty); // undefined
```

- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/seal
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/freeze

## III. Iterating over object properties
The `for...in` loop is commonly used to iterate over object properties.

Add the following to **objects-1.html**:

```
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

## IV. Adding behavior to our objects

Objects usually have *state* (properties or instance variables) AND *behavior* (methods).

Can we add behavior to our JavaScript object literals? You betcha!

### objects-2.html

```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title>Objects-2</title>
</head>
<body>
<script>

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

## V. Creating "object factories"
What if we had a game that needed to have 50 cars driving around? Creating 50 object literals - `car1 = {...} ,car2 = {...}, car3 = {...}` would be both tedious and error prone.
Instead, we can create a function to create these cars for us.

### objects-3.html
```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title>Objects-3</title>
</head>
<body>
<script>

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
	console.log(car);	
}
</script>
</body>
</html>
```

