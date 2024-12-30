> [!INFO]
> Information about a `user` stored in a user's web-browser
> Examples: 
> - Targeted Advertisements,
> - Browsing Preferences
> - Other non-sensitive data

```php

setcookie("fav_food", "pizza", time() + (86400 * 2), "/"); // Expires in 2 days
setcookie("fav_drink", "coffee", time() + (86400 * 3), "/"); // Expires in 3 days
setcookie("fav_food", "ice cream", time() + (86400 * 4), "/"); // Expires in 4 days
```

#### Deleting Cookies
```php
setcookie("fav_food", "pizza", time() - 0, "/");
```

#### Printing `key` & `value` pair from COOKIES

```php
foreach($_COOKIE as $key => $value) {
	echo "{$key} = {$value} <br>";
}
```
output:
![[Pasted image 20240320130009.png]]
EXAMPLE:
```php
if(isset($_COOKIE["fav_food"])) {
	echo "BUY SOME {$_COOKIE["fav_food"]} !!!";
} else {
	echo "I don't know you favorite food"
}
```