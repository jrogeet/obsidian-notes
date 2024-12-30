
>[!INFO]
>Super Global Variable 
>- Contains `headers`, `paths`, and `script` locations.
>- __Entries__ in this `array` are __created__ by the ___web server___
>- Shows __Nearly everything__ you need to know about the ___Current Web Page Environment___

```php
foreach ($_SERVER as $key => $value) {
	echo "{$key} = {$value} <br>";
}
```



#### Action

If we set the `action="file.php"` to a certain `php file`,
then __Changed it__, It will cause a `NOT FOUND` Error.
```php
// index.php
<body>
	<form action="home.php" method="post">
		username:<br>
		<input type="text" name="username">
		<input type="submit">
	</form>
</body>
```

To automatically change it's file name of the __Current File__:
```php
<body>
	<form action="<?php $_SERVER["PHP_SELF"]?>" method="post">
		username:<br>
		<input type="text" name="username">
		<input type="submit">
	</form>
</body>
```
- Vulnerable to __CROSS SITE SCRIPT__
	- Solution: `htmlspecialchars()`
		- Avoids __Cross Site Script__
```php
	<form action="<?php htmlspecialchars($_SERVER["PHP_SELF"]) ?>" method="post">
```


#### Method
```php
if($_SERVER["REQUEST_METHOD"] == "POST") {
	echo "HELLO";
}
```