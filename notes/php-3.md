# 3 - PHP Arrays

## Contents
<!--- Local Navigation --->
I. [Overview](#section1)
II. [Creating indexed arrays](#section2)
III. [Array functions](#section3)

## I. <a id="section1">Overview
  
## II. <a id="section2">Creating indexed Arrays

**php-arrays-1.php**
```
<?PHP
 	// 1 - Indexed arrays - there are a two ways to initialize one
 	
 	// A - the array() function will create an array
 	$schools = array("RIT","RPI","MCC");
 	
 	// B - specify an array literal
 	$colors = ["red","green","blue"];
 	
 	// 2 - access elements with []
 	echo "<p>First \$school is " .  $schools[0] . "</p>";
 	
 	// curly braces around the array let us use string interpolation
 	echo "<p>Second \$color is {$colors[1]}</p>";
 	
 	// 3 - to debug your arrays, use one of these functions
 	
 	echo "<pre>";
 	var_dump($schools);
 	echo "</pre>";
 	
 	echo "<pre>";
 	print_r($colors);
 	echo "</pre>";
 	
?>
```

## III. <a id="section3">Array functions
Arrays in PHP are not objects like you see in many other languages, but are instead what PHP calls *resources*. 
- In many languages we might access the length of an array through a property like this `myArray.length`
- But in PHP, we instead use a pre-defined function, and pass in the array as an argument like this `count($myArray)`

 **php-arrays-2.php**
 ```
<?PHP
	$colors = ["red","green","blue"];
 	$length =  count($colors);
 	echo "<p>The length of \$colors is $length</p>";
?>
 ```
 
 
 Other operations you can do include adding and removing elements from an array:
  **php-arrays-3.php**
 ```
 
 ```
 
  And sorting arrays:
  **php-arrays-4.php**
 ```
 
 ```
 
 
 There are many more functions that operate on arrays - you can find a full list here: http://php.net/manual/en/ref.array.php

<hr><hr>

**[Previous Chapter <- PHP Scalars & Data Types (chapter 2)](php-2.md)**

**[Next Chapter -> PHP Functions (chapter 4)](php-4.md)**
