Prevent __USER INPUT__ that is a `CODE` from __EXECUTING__ when inputted.


### Sanitize
If __Invalid__: Returns an `Empty String` `" "`
```php
// INSTEAD OF:
// (which could run a JavaScript code when used as an INPUT)
$username = $_POST["username"];


// filter out the input, resulting to a raw string
// INPUT_POST or INPUT_GET
$username = filter_input(INPUT_POST, "username", FILTER_SANITIZE_SPECIAL_CHARS);
```

- Filter __NUMBERS:__
```php
$age = filter_input(INPUT_POST, "age", FILTER_SANITIZE_NUMBER_INT);
// sample input: wdaiiawei93ajw
echo $age; // 93
```

- Filter __EMAIL__:
```php
$email = filter_input(INPUT_POST, "email", FILTER_SANITIZE_EMAIL); 
// sample input: <BroCode@gmail.com>()
echo $email; // BroCode@gmail.com
```


### Validate
If __Invalid__: Returns `false`

- Validate `Integer`Input:
```php
$age = filter_input(INPUT_POST, "age", FILTER_VALIDATE_INT);
```

- Validate `EMAIL`:
```PHP
$email = filter_input(INPUT_POST, "email", FILTER_VALIDATE_EMAIL);
```
