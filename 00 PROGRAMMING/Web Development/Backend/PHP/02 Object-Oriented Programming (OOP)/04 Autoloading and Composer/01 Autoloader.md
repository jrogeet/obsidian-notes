---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 
> [!INFO]
> - Helps in Code readability,
> 	- Doesn't need to put `include` or `requires`
> - Automatically loads `classes`, `interfaces` or `traits` that are ___not included or defined___


```php
spl_autoload_register(function($class) {
	var_dump('Autoloader 1:');
});

spl_autoload_register(function($class) {
	var_dump('Autoloader 2:');
}, prepend: true); // Prepend set to TRUE, means this would run FIRST


use App\PaymentGateway\Paddle\Transaction;

$paddleTransaction = new Transaction();

var_dump($paddleTransaction);
```


>[!example] `require` a path inside `autoloader`
>```php
>spl_autoload_register(function($class) {
>	
>	$path = __DIR__ . '/../' . lcfirst(str_replace('\\', '/', $class)) . '.php';
>
>	require $path;
>});
>
>use App\PaymentGateway\Paddle\Transaction;
>
>$paddleTransaction = new Transaction();
>
>var_dump($paddleTransaction);
>```
>- `__DIR__` is a __Magic Function__
>- `lcfirst()` - Lower Cases the First Letter
>- `str_replace()` - Replaces _backslash_ with __Normal Slash__
