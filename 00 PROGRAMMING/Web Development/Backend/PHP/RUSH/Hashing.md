> [!info] Hashing
> - Transforming sensitive data (`password`)
> - Into __Letters__, __numbers__, and/or __Symbols__
> - via ___Mathematical Process___ (Similar to _Encryption_)
> - __Hides__ the `original data` from __3rd Parties__

---

```php
$password = "pizza123";

$hash = password_hash($password, PASSWORD_DEFAULT);
// PASSWORD_DEFAULT is one of the hashing methods in PHP
// it uses bcrypt algorithm
```

#### Check if a `password` matches a `hash`
`password_verify`

```php

if(password_verify("hotdog1212", $hash)) { // FALSE, Incorrect
	echo "You are logged in!";
} else {
	echo "Incorrect password!";
}

```