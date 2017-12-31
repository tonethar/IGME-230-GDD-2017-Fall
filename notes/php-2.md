# 2 - PHP Scalars & Data Types

## Contents
<!--- Local Navigation --->
I. [PHP Types](#section1)

II. [PHP Variables](#section2)

III. [Integers & Floats](#section3)

IV. [Booleans](#section4)

V. [Strings](#section5)

VI. [Type Coercion](#section6)

VII. [Constants](#section7)

VIII. [Operators](#section8)


## I. <a id="section1">PHP Types
- PHP has 4 *scalar* (i.e. "primitive") types: integer, float (aka double), string and boolean
- PHP has 2 *composite* types: array and object
- PHP has 2 *special* types: resource and null

## II. <a id="section2">PHP Variables
- variables in PHP are denoted with a leading dollar sign `$`
- variable names must begin with a letter or underscore character
- variables can, but do not need, to be declared before assignment
- variables do not have intrinsic *types* - a variable does not know in advance whether it will be used to store a number or a string or something else
- PHP does a good job of automatically converting types from one to another when necessary

## III. <a id="section3">Integers & Floats
Run the following code and observe the results:
  
**php-types-1.php**
```php
<?PHP
	// add integers
	$a = 1;
	$b = 2;
	$c = $a + $b;
	echo "<p>The sum of integers $a and $b is $c</p>";
	
	// explicit casting
	$a = 1;
	$b = 2.99;
	$c = $a + (int)$b;
	echo "<p>The sum of integers $a and $b is $c</p>";
	
	// add floats
	$a = 1.0;
	$b = 2.0;
	$c = $a + $b;
	echo "<p>The sum of floats $a and $b is $c</p>";
	
	$a = 1.0;
	$b = 2.99;
	$c = $a + $b;
	echo "<p>The sum of floats $a and $b is $c</p>";
?>
```
  
## IV. <a id="section4">Booleans
Run the following code and observe the results:

**php-types-2.php**
```php
<?PHP
  $phpIsWeird = TRUE;
  if ($phpIsWeird){
  	echo("<p>PHP is REALLY weird!</p>");
	}else{
   	echo("<p>PHP is NOT weird!</p>");
  }
  
  $ritIsWeird = 0; // 0 and 0.0 are false, all other numbers coerce to TRUE
  if ($ritIsWeird){
  	echo("<p>RIT is REALLY weird!</p>");
	}else{
   	echo("<p>RIT is NOT weird!</p>");
  }
  
  $rochesterIsWeird = ""; // empty strings "" and '' are FALSE
  if ($rochesterIsWeird){
  	echo("<p>Rochester is REALLY weird!</p>");
	}else{
   	echo("<p>Rochester is NOT weird!</p>");
  }
  
  $gccisIsWeird = []; // empty array is FALSE
  if ($gccisIsWeird){
  	echo("<p>GCCIS is REALLY weird!</p>");
	}else{
   	echo("<p>GCCIS is NOT weird!</p>");
  }
  
  $thisDemoIsDone = "XYZPDQ"; // most everything else is TRUE
  if ($thisDemoIsDone){
  	echo("<p>This demo is DONE!</p>");
	}else{
   	echo("<p>This demo is NOT DONE!</p>");
  }
?>
```


More here: https://stackoverflow.com/questions/2382490/how-does-true-false-work-in-php
  
## V. <a id="section5">Strings
Run the following code and observe the results:

**php-types-3.php**
```php
<?PHP
  // string values may be single or double quoted
  $name = 'Fred';
  $name = "Fred";
   
  // strings may be concatenated with a dot (period)
  $greeting1 = "<p>My name is " . $name . "</p>";
   
  // string variables WILL be interpolated in a double-quoted string
  $greeting2 = "<p>My name is $name</p>";
   
  // string variables WILL NOT interpolate in a single-quoted string
  $greeting3 = '<p>My name is $name</p>';
  
  echo($greeting1);
  echo($greeting2);
  echo($greeting3);
?>
```

## VI. <a id="section6">Type Coercion
PHP does not require (or support) explicit type definition in variable declaration; a variable's type is determined by the context in which the variable is used. That is to say, if a string value is assigned to variable `$var`, `$var` becomes a string. If an integer value is then assigned to `$var`, it becomes an integer.
  
 **The code below works as expected in PHP 5, but the automatic string conversion produces warnings in PHP 7:**
 
  **php-types-4.php**
 ```php
 <?php
	// In PHP 5, these run as follows
	$foo = "1";  				// $foo is string (ASCII 49)
	$foo *= 2;   				// $foo is now an integer (2)
	$foo = $foo * 1.3;  // $foo is now a float (2.6)
	$foo = 5 * "10 Little Piggies"; 	// $foo is integer (50) *
	$foo = 5 * "Small Pigs = 10";     // $foo is integer (0)	**
	echo $foo;
	

// * In PHP 7, this currently gives an error: "A non well formed numeric value encountered"
	
// ** In PHP 7, this currently gives an error: "A non-numeric value encountered"	
?>
```

**The solution - PHP 7, you will need to *explicitly cast* the strings to integers with `(int)` to avoid the errors:**
 
**php-types-5.php**
 ```php
 <?php
	// In PHP 7, get rid of the errors by casting
	$foo = "1";  				// $foo is string (ASCII 49)
	$foo *= 2;   				// $foo is now an integer (2)
	$foo = $foo * 1.3;  // $foo is now a float (2.6)
	$foo = 5 * (int)"10 Little Piggies"; 	// $foo is integer (50)
	$foo = 5 * (int)"Small Pigs = 10";     // $foo is integer (0)
	echo $foo;
?>
```



Read more here: http://php.net/manual/en/language.types.type-juggling.php 

## VII. <a id="section7">Constants
  
 ```php
 <?PHP
  
 ?>
 ```
 
 ## VIII. <a id="section8">Operators
  
 ```php
 <?PHP
  
 ?>
 ```

