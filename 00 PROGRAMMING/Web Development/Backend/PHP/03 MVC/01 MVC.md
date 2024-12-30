---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 
> [!info] M.V.C.
> _Model_, __View__, ___Controller___
> ![[Pasted image 20240330184412.png]]
> ![[Pasted image 20240330200228.png]]
> ![[Pasted image 20240330200340.png]]
> ![[Pasted image 20240330200709.png]]
>> [!info] _Model_
>>Handles the Business Logic
>> - Manages the `DATA` of the application (`DATA` MANAGEMENT)
>> 	- Process and Store `DATA`
>> 		- `DATA` can be stored in a __DATABASE__ or any __DATA STRUCTURE__
>
>> [!info] __View__
>> __View__ rendered and displayed in the `Screen`/`Browser`/`Client`
>> ___Controller___ passes `DATA`or Information to the __View__
>> - PHP file with `HTML/React etc.` in it
>
>> [!info] ___Controller___
>> - Requests to the `SERVER` goes to the ___Controller___
>> 	- Requests
>> 	- Responses
>> 	- Handle resources


---
>[!example]
> _public/index.php_:
> ```php
> require_once __DIR__ .'/../vendor/autoload.php';
> 
> session_start();
> 
> define('STORAGE_PATH', __DIR__ . '/../storage');
> define('VIEW_PATH', __DIR__ . '/../views');
> 
> $router = new App\Router();
> 
> $router
>	->get('/', [App\Classes\Home::class, 'index'])
>	->post('/upload', [App\Classes\Home::class, 'upload'])
>	->get('/invoices', [App\Classes\Invoice::class, 'index'])
>	->get('/invoices/create', [App\Classes\Invoice::class, 'create'])
>	->post('/invoices/create, [App\Classes\Invoice::class, 'store']);
>	
>echo $router->resolve(
>	$_SERVER['REQUEST_URI'],
>	strtolower($_SERVER['REQUEST_METHOD'])
>);
> ```
> 
>_HomController.php_
>```php
>namespace App\Controllers;
>
>use App\View;
>
>class HomeController
>{
>	// public function index(): string
>	public function index(): View
>	{
>		// return (new View('index'))->render();
>		// return (string) View::make('index');
>		return View::make('index');
>	}
>	
>	public function upload()
>	{
>		$filePath = STORAGE_PATH  . '/' . $_FILES['receipt']['name'];
>		
>		move_upload_files($_FILES['receipt']['top_name'], $filePath);
>		
>		echo '<pre>';
>		var_dump(pathinfo($filePath));
>		echo '</pre>';
>	}
>}
>```
>
>_InvoiceController.php_:
>```php
>namespace App\Controllers;
>
>use App\View;
>
>class InvoiceController
>{
>	public function index(): View
>	{
>		return View::make('invoices/index');
>	}
>	
>	public function create(): View
>	{
>		return View::make('invoices/create');
>	}
>	
>	public function store()
>	{
>		$amount = $_POST['amount'];
>		
>		var_dump($amount);
>	}
>}
>```
>
>_View.php_
>```php
>declare(strict_types = 1);
>
>namespace App;
>
>class View
>{
>	public function __construct(protected string $view, protected array $params = []) {
>	
>	}
>	
>	public static function make(string $string, array $params = []): static
>	{
>		return new static($view, $params);
>	}
>	
>	public function render(): string
>	{
>		ob_start(); // Turns On OUTPUT BUFFERING
>		
>		// include $this->view; WONT WORK (Relative, Not Full path)
>		
>		// What if this view below doesn't exist?
>		// include VIEW_PATH . '/' . $this->view . '.php';
>		
>		$viewPath = VIEW_PATH . '/' . $this->view . '.php';
>		
>		if(! file_exists($viewPath)){
>			throw new ViewNotFoundException();
>		}
>		
>		
>		return (string) ob_get_clean();
>	}
>	
>	public function __toString(): string
>	{
>		return $this->render();
>	}
>}
>```
> - As soon as `include` in the `render()` method is reached,  it will load the __script__
> 	- Which is NOT IDEAL, since what if we want to run some code afterwards
> 	- or run some code before outputting it in the screen
> - `ob_get_clean()` - Gets the `content` of the __Internal Buffer__ and cleans it up after.
>_views/index.php_:
>```php
><form action="/upload" method="post" enctype="multipart/form">
>	<input type="file" name="receipt" />
>	<button type="submit">Upload</button>
></form>
>```


