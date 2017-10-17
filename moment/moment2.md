# Printing #

```php
<?php
echo "<h1>Header using echo</h1>";
// Echo is marginally faster than print
print "<h1>Header using print</h1>";
// But print has a return value
?>
```
<script src="//repl.it/embed/KkFe/6.js"></script>

# Comments #

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

# Variables #

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

# Constants #

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

# Concatenation #

```php
<?php
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

# Strings #

```php
<?php
// Since this won't be run in a browser, "<br>" won't do anything.
// For this reason I've also included a newline so that it is readable.
echo "PHP is about as interesting as \"escaped quotes\"<br>\n";
echo "Take that as you wish<br>\n";
?>
```
<script src="//repl.it/embed/MkZW/0.js"></script>

# String Functions #

```php
<?php
$foo = "WebserverProgramming 1";

echo strlen($foo)."\n";
echo strtolower($foo)."\n";
$bar = strtoupper($foo); // Saving this for later.
echo $bar."\n";
echo strrev($foo)."\n";
echo str_replace("Webserver", "PHP-", $foo)."\n"; // I don't understand why PHP mixes
echo strcmp($bar, $foo)."\n";                     // camelcase and snake case.
echo strcasecmp($bar, $foo)."\n";
$foo = "You can change the contents of variables";
echo $foo."\n";
?>
```

<script src="//repl.it/embed/KyUm/0.js"></script>

# Array #

```php
<?php
class User { // Might as well go overkill. Not to mention that this is a more long-term solution
  function __construct($FirstName = "Undefined", $LastName = "Undefined", $Email = "Undefined") {
    //Default values
    $this->firstName = $FirstName;
    $this->lastName = $LastName;
    $this->email = $Email;
  }

  function printf() {
    //There are a ton of ways that I could have done this, but this felt the simplest
    printf("%s %s has the email address '%s'\n", $this->firstName, $this->lastName, $this->email);
  }
}

$users = Array(
  new User("Bob", "The Builder", "bob@builder.co.com.uk.io"),
  new User("Jim", "John", "jim.johnsson@hotmail.com"),
  new User("Yeong-Su", "Origen Bonfils", "jeff@g-mail.dog"), //Yes that's a real TLD
);

foreach ($users as $key => $user) {
  $user->printf(); // I don't know what it is with PHP and arrows
}
?>
```
<script src="//repl.it/embed/MkZh/0.js"></script>

# Bonus #

```php
<?php
$string = 'Programming is "fun"'; //Using single quotes to not have to escape the double quotes
$array = array();

$array['We are working with the string "%s".'] = $string; //Again using single quotes for this reason
$array['The string is %d characters long.'] = strlen($string); //And then keep using them for consistency
$array['The first space is at character %d.'] = strpos($string, " ");
$array['The first word is "%s".'] = explode(" ", $string, 2)[0];
$array['%s'] = sprintf("%s %s", strtoupper(explode(" ", $string, 2)[0]), explode(" ", $string, 2)[1]);
$array[10] = "Football is the best sport."; //The assignment never told me to print this one, so I won't

// I realize that there are a ton of issues with this solution (such as a single string only being
// useable once), but it's obivously not a very important scenario.

foreach ($array as $index => $row) {
  if (!is_numeric($index)) {
    printf($index."\n", $row);
  }
}
?>
```
<script src="//repl.it/embed/LlJo/2.js"></script>
