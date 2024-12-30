---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 

> [!abstract]
> - ___GET___ used when (___Fetching Data___)
> 	- Retrieving `Data`
> 	- Viewing something
> - __POST__ used when (__Updating Data__)
> 	- Store `Data`
> 	- Make Changes to `Data`


> [!info] `$_GET`
> ![[Pasted image 20240330132426.png]]
> ```php
> var_dump($_GET);
> ```
> ![[Pasted image 20240330132521.png]]

> [!info] `$_POST`
> ```php
> var_dump($_POST);
> 
> <form action="/" method="post"><label>Amount</label><input type="text" name="amount"></form>
> ```
> ![[Pasted image 20240330132806.png]]
> ![[Pasted image 20240330132820.png]]
>> [!tip] Append data to the __Query String__
>> ```php
>> <form action="/?foo=bar" method="post"><label>Amount</label><input type="text" name="amount"></form>
>> ```
>> ![[Pasted image 20240330132806.png]]
>> ![[Pasted image 20240330132955.png]]
>> 
>> ---
>> ```php
>> // added amount=250
>> <form action="/?foo=bar&amount=250" method="post"><label>Amount</label><input type="text" name="amount"></form>
>> ```
>> ![[Pasted image 20240330133236.png]]


> [!info] `$_REQUEST`
> - Contains values from `$_GET`, `$_POST` and `$_COOKIE`
> PS. Applied to the codes above
> ```php
> var_dump($_REQUEST);
> ```
> ![[Pasted image 20240330133446.png]]
> - If `keys` are __the same__ from both `$_GET` AND `$_POST`,
> 	- __POST__ will take precedence!

--- 
>[!example]
>_index.php_
>```php
>require_once __DIR__ . '/../vendor/autoload.php';
>
>$router = new App\Router();
>
>$router
>	->get('/', [App\Classes\Home::class, 'index'])
>	->get('/invoices', [App\Classes\Invoice::class, 'index'])
>	->get('/invoices/create', [App\Classes\Invoice::class, 'create']);
>	->post('/invoices/create', [App\Classes\Invoice::class, 'store']);
>	
>echo $router->resolve($_SERVER['REQUEST_URI'], strtolower($_SERVER['REQUEST_METHOD']));
>```
>- `->register('/', [App\Classes\Home::class, 'index'])`
>	- `'/'` - the path
>	- `[App\Classes\Home::class, 'index']`
>		- `App\Classes\Home::class` - the ___class___ file
>		- `'index` - the __method__ name
>
> _Router.php_
> ```php
> declare(strict_types=1);
> 
> namespace App;
> 
> class Router
> {
> 	private array $routes;
> 	
> 	// added array
> 	public function register(string $requestMethod, string, $route, callable | array $action): self
> 	{
> 		$this->routes[$requestMethod][$route] = $action;
> 		
> 		return $this;
> 	}
> 	
> 	public function get(string, $route, callable | array $action): self
> 	{
> 		return $this->register('get', $route, $action);
> 	}
> 	
> 	public function post(string, $route, callable | array $action): self
> 	{
> 		return $this->register('post', $route, $action);
> 	}
> 	
> 	public function routes(): array
> 	{
> 		return $this->routes;
> 	}
> 	
> 	public function resolve(string $requestUri, string $requestMethod)
> 	{
> 		$route = explode('?', $requestUri)[0];
> 		
> 		$action = this->$routes[$requestMethod][$route] ?? null;
> 		
> 		if (! $action) {
> 			throw new RouteNotFoundException();
> 		}
> 		
> 		
> 		if (is_callable($action)) {
> 			return call_user_func($action);
> 		}
> 		
> 		if (is_array($action)){
> 			[$class, $method] = $action;
> 			
> 			if (class_exists($class)) {
> 				$class = new $class();
> 				
> 				if (method_exists($class, $method)) {
> 					return call_user_func_array([$class, $method], []);
> 				}
> 			}
> 		}
> 		
> 		throw new RouteNotFoundException();
> 	}
> }
> ```
> 
> _Home.php_
> ```php
> declare(strict_types=1);
> 
> namespace App\Classes;
> 
> class Home
> {
> 	public function index(): string
> 	{
> 		return 'Home';
> 	}
> }
> ```
> 
> _Invoice.php_
> ```php
> declare(strict_types=1);
> 
> namespace App\Classes;
> 
> class Invoice
> {
> 	public function index(): string
> 	{
> 		return 'Invoices';
> 	}
> 	
> 	public function create(): string
> 	{
> 		return <form action="/invoices/create" method="post"><label>Amount</label><input type="text" name="amount"></form>
> 	}
> 	
> 	public function store()
> 	{
> 		$amount = $_POST['amount'];
> 		
> 		var_dump($amount);
> 	}
> }
> ```
