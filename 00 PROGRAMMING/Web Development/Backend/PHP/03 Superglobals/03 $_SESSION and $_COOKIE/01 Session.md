---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 

> [!info]
> - __SESSIONS__ :
> 	- Stored in Server Side
> 	- Destroyed upon closing the browser
> - ___COOKIES___ :
> 	- Stored in Client Side
> 	- Remain as long as the `Expiration date`
> 		- Or when ___cookies___ are deleted.

> [!info] __SESSIONS__
> - Must be started __before any `Output`__
> 
> ```php
> session_start();
> ```
> - When __Session__ is started, it __creates a `Unique Session ID`__
> 	- and it writes it on ___Cookie___
> ![[Pasted image 20240330164729.png]]
> ![[Pasted image 20240330164826.png]]
> 
>> [!tip] 
>> _Home.php_
>> ```php
>> declare(strict_types=1);
>> 
>> namespace App\Classes;
>> 
>> user App\View;
>> 
>> class Home
>> {
>> 	public function index(): string
>> 	{
>> 		$_SESSION['count'] = ($_SESSION['count'] ?? 0) + 1;
>> 		return View::make('index', $_GET)->render();
>> 	}
>> }
>> ```
>> _index.php_
>> ```php
>> session_start();
>> 
>> $router = new App\Router();
>> 
>> $router
>> 	->get('/', [App\Classes\Home::class, 'index'])
>> 	->get('/invoices', [App\Classes\Invoice::class, 'index'])
>> 	->get('/invoices/create', [App\Classes\Invoice::class, 'create'])
>> 	->post('/invoices/create', [App\Classes\Home::class, 'store']);
>> 	
>> echo $router->resolve(
>> 	$_SERVER['REQUEST_URL'],
>> 	strtolower($_SERVER['REQUEST_METHOD'])
>> );
>> 
>> var_dump($_SESSION);
>> ```
>> - Everytime _Home_ Page is visited/reloaded, the __Counter__ INCREMENTS
>> 	- It can be removed by deleting the ___Cookie___
>> 	- Or using `unset` on it
>> ```php
>> unser($_SESSION['count']);
>> ```



