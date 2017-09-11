# Printing

```php
<?php
echo "<h1>Header using echo</h1>";
// Echo is marginally faster than print
print "<h1>Header using print</h1>";
// But print has a return value
?>
```
<script src="//repl.it/embed/KkFe/6.js"></script>

# Comments

```php
<?php
echo "Here's an example of a single line comment:";
// Single line comment

echo "Here is an example of a multiline comment:";
/*
*Multi
*line
*comment
*/
?>
```
<script src="//repl.it/embed/Kuvu/0.js"></script>

# Variables

```php
<?php
// Circle math
$radius = 4;

// Oh and there's a constant for Pi, I don't have to approximate it.
$circumfrence = 2 * M_PI * $radius;
$area = M_PI * $radius * $radius;

echo "With a radius of $radius, the area is $area and the circumfrence $circumfrence.";
?>
```
<script src="//repl.it/embed/KuwR/0.js"></script>

# Constants

```php
<?php
// I solved the last problem before looking at this one,
// and I already found the constant for Pi.

define("VAT", 1.25);

$price = 850;
$finalPrice = $price * VAT;

echo "Final price is $finalPrice";
?>
```
<script src="//repl.it/embed/Kuw2/0.js"></script>

# Concatenation

```php
$radius = 4;

$circumfrence = 2 * M_PI * $radius;
$area = M_PI * $radius * $radius;

// Using the variables within the string.
echo "If the radius is $radius then the area is $area and the circumfrence is $circumfrence.\n";

// Concatenating the strings and the variables
echo "If the radius is ".$radius." then the area is ".$area." and the circumfrence is ".$circumfrence."\n";
?>
```
<script src="//repl.it/embed/Kuwc/0.js"></script>
