[Back](../index.md)

# Functions #

<iframe height="400px" width="100%" src="https://repl.it/@LfourZ/DisguisedWellwornIbex?lite=true" scrolling="no" frameborder="no" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals" width="100%" ></iframe>

# Functions Part II #

<iframe height="400px" width="100%" src="https://repl.it/repls/ChubbyHelpfulEchidna?lite=true" scrolling="no" frameborder="no" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

# Functions Part III #

<iframe height="400px" width="100%" src="https://repl.it/@LfourZ/EnviousWaterloggedEquestrian?lite=true" scrolling="no" frameborder="no" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals" width="100%" ></iframe>

# Form #

[Try it out](http://83.241.151.251:35005/form.php)

```php
<html lang="en">
  <head>
    <style>
      body {
        text-align: center;
      }
    </style>
  </head>
  <body>
    <form method="post">
      <p>First name <input type="text"     name="firstName" required="true"></p>
      <p>Last name  <input type="text"     name="lastName"  required="true"></p>
      <p>Birth date <input type="date"     name="birthDate" required="true"></p>
      <p>Password   <input type="password" name="password"  required="true"></p>
      <p>
        Male  <input type="radio" name="gender" value="male" required="true">
        Female<input type="radio" name="gender" value="female">
      </p>
      <input type="checkbox" name="agree" required="true">I agree that PHP is garbage<br>
      <input type="submit" name="submit" value="Submit">
    </form>
    <?php
      echo "Hello, ".$_POST["firstName"]." ".$_POST["lastName"]."<br>";
      echo "sha512 hash of password: ".hash("sha512", $_POST["password"])."<br>";
      echo "Birth date: ".$_POST["birthDate"]."<br>";
      echo "Gender: ".$_POST["gender"]."<br>";
      $agreed = "no";
      if ($_POST["agree"] == "on") {
        $agreed = "yes";
      }
      echo "Agreed to TOC: ".$agreed."<br>";
    ?>
    <div class="calculator" <?php if ($_POST["submit"] != "Submit") {?> style="display:none" <?php } ?>>
      <form method="get" action="calculator.php">
        <!-- Calculator.php
        <?php
        $radius = $_GET["radius"];
        echo "Radius: ".$radius."<br>";
        echo "Area: ".(M_PI * $radius * $radius)."<br>";
				echo "Circumfrence: ".(M_PI * 2 * $radius);
        ?>
        -->
        <p>Radius <input type="number" name="radius" required="true"></p>
        <input type="submit" name="getRadius">
      </form>
    </div>
  </body>
</html>
```
