
> [!info]
> A Super Global Variable
> - Used to ___store information on a user___ to be __used across multiple pages__.
> 	- A user is assigned a `session-id`
> EXAMPLE:
> - Login Credentials


Before the `HTML code`:

__Session__ should be STARTED FIRST
```php
<?php
	session_start();
?>

// HTML CODE

<?php

?>
//php again
```

> [!example]
> 2 php files
> File 1: `index.php`
> ```php
> <?php
> 	session_start();
> ?>
> 
> // HTML CODE
> 
> <?php
> $_SESSION["username"] = "BroCode";
> $_SESSION["password"] = "pizza123";
> 
> echo $_SESSION["username"] . "<br>";
> echo $_SESSION["password"] . "<br>";
> ?>
> ```
> 
> File 2: `home.php`
> 
> <?php
> session_start();
> ?>
> ```php
> <?php
> 	session_start();
> ?>
> // HTML CODE
> 
> <? php
> echo $_SESSION["username"] . "<br>";
> echo $_SESSION["password"] . "<br>";
> ?>
> ```

---


> [!example]
> 
> File 1: `index.php`
> ```php
> <?php
> session_start(); 
> ?>
> 
> // HTML
> <body>
> 	 <form action = "index.php" method = "post"> 
> 		 username: <br>
> 		 <input type = "text" name="username"><br>
> 		 password: <br>
> 		 <input type="password" name="password"><br>
> 		 <input type="submit" name="login" value="login">
> 	 </form>
> </body>
> 
> <?php
> if(isset($_POST["login"])){ // IF login button is clicked
> 	if(!empty($_POST["username"]) && 
> 		!empty($_POST["password"])) { // And Username and Password field is NOT EMPTY
> 			$_SESSION["username"] = $_POST["username"]; // Assign Username
> 			$_SESSION["password"] = $_POST["password"]; // and Password to SESSION
> 		
> 			header("Location: home.php"); // REDIRECTS to home.php
> 		} else {
> 			echo "Missing username/password <br>"
> 		}
> }
> ?>
> ```
> 
> File 2: `home.php`
> ```php
> <?php 
> session_start();
> ?>
> 
> // HTML
> <form action="home.php" method="post">
> 	<input type="submit" name="logout" value="logout">
> </form>
> 
> <?php
> 	 echo $_SESSION["username"] . "<br>";
> 	 echo $_SESSION["password"] . "<br>";
> 	 
> 	 if(isset($_POST["logout"])) {
> 		 session_destroy();
> 		 header("Location: index.php");
> 	 }
> ?>
> ```

