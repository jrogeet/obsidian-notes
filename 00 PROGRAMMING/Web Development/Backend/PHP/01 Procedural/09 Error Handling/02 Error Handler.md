---
topic: php
---


Tags/Topics: #php #error
∗:[[0 PHP|PHP]]

---
# Design

--- 

> [!example] Custom error handler & `set_error_handler`
> - First argument, the __Custom Error Handler__
> - Second argument, the __ERROR LEVEL__
> ```php
> function errorHandler (
> 	int $type, // ERROR TYPE
> 	string $msg, // ERROR MESSAGE
> 	?string $file = null, // FILE
> 	?int $line = null // and LINE WHERE THE ERROR HAPPENS
> ) {
> 	// the NEXT LINE is not advisable, because you don't want to EXPOSE ERRORS to USERS
> 	// FOR DEMOSTRATION ONLY
> 	echo $type . ': ' . $msg . ' in ' . $file . ' on line ' . $line;
> 
> 	// return;
> 	exit; // STOPS SCRIPT FOR FATAL ERRORS
> }
> 
> error_reporting(E_ALL & ~E_WARNING);
> 
> set_error_handler('errorHandler', E_ALL);
> 
> echo $x;
> ```
