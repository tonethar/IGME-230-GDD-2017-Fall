# 2 - PHP Scalars & Data Types

## Contents
<!--- Local Navigation --->
I. [PHP Types](#section1)

II. [PHP Variables](#section2)

III. [Integers & Floats](#section3)

IV. [Booleans](#section4)

V. [Strings](#section5)

VI. [Type Coercsion](#section6)


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
  
  ```php
  <?PHP
  
  ?>
  ```
  
## V. <a id="section5">Strings
  
  ```php
  <?PHP
  
  ?>
  ```

## VI. <a id="section6">Type Coercsion
  
    ```php
  <?PHP
  
  ?>
  ```

