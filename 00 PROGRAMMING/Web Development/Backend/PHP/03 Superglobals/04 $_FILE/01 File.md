---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 

> [!info]
> ```php
> declare(strict_types = 1);
> 
> namespace App\Classes;
> 
> class Home
> {
> 	public function index(): string
> 	{
> 		return <<<FORM
> 		<form action="/upload" method="post" enctype="multipart/form-data">
> 			<input type="file" name="receipt" />
> 			<button type="submit">Upload</button>
> 		</form>
> 		FORM;
> 	}
> 
> 	public function upload()
> 	{
> 		echo '<pre>';
> 		var_dump($_FILES);
> 		echo '</pre>';
> 	}
> }
> ```
> ___OUTPUT___ of the `var_dump($_FILES);`
> ![[Pasted image 20240330172943.png]]
> 
> _index.php_
> ```php
> session_start();
>
>$router = new App\Router();
>
>$router
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

> [!tip] Where are the FILES stored?
> ![[Pasted image 20240330174342.png]]
> `Files` uploaded in PHP are stored TEMPORARILY in the server's __default tmp directory__
> >  Can be changed in `php ini configuration file`
> - In the end of the request,  `files` from the __tmp directory__ are ___DELETED___
> 	- Upload `files` to the CLOUD like __S3__
> 	- or Local Directory
> 
> ```php
> $filePath = STORAGE_PATH . '/' . $_FILES['receipt']['name'];
> 
> move_uploaded_file($_FILES['receipt']['tmp_name'], $filePath);
> 
> echo '<pre>';
> var_dump(pathinfo($filePath));
> echo '</pre>';
> ```
> _index.php_ or the __Main Application `Class`__:
> ```php
> define('STORAGE_PATH', __DIR__, '/../storage');
> ```
> ___OUTPUT___:
> ![[Pasted image 20240330180444.png]]
> 
>   -__Storage Path__
> 	 - Could either be Hard-Coded
> 	 - or Create a `constant` in the __Main Application `Class`__

> [!example] Upload __MULTIPLE FILES__
> ```php
> declare(strict_types = 1);
> 
> namespace App\Classes;
> 
> class Home
> {
> 	public function index(): string
> 	{
> 		return <<<FORM
> 		<form action="/upload" method="post" enctype="multipart/form-data">
> 			<input type="file" name="receipt" />
> 			<input type="file" name="myimage" />
> 			<button type="submit">Upload</button>
> 		</form>
> 		FORM;
> 	}
> 
> 	public function upload()
> 	{
> 		echo '<pre>';
> 		var_dump($_FILES);
> 		echo '</pre>';
> 		
> 		$filePath = STORAGE_PATH . '/' . $_FILES['receipt']['name'];
> 
> 		move_uploaded_file($_FILES['receipt']['tmp_name'], $filePath);
> 
> 		echo '<pre>';
> 		var_dump(pathinfo($filePath));
> 		echo '</pre>';
> 	}
> }
> ```
> ___OUTPUT___: 
> ![[Pasted image 20240330182507.png]]
> 
>> [!tip] Storing in an `Array`
>> 
>> ```php
>>  // ...
>> class Home
>>{
>> 	public function index(): string
>> 	{
>> 		return <<<FORM
>> 		<form action="/upload" method="post" enctype="multipart/form-data">
>> 			<input type="file" name="receipt[]" />
>> 			<input type="file" name="receipt[]" />
>> 			<button type="submit">Upload</button>
>> 		</form>
>> 		FORM;
>> 	}
>> 	// ...
>> ```
>> 
>> - Added Square brackets `[ ] ` on the `name=""`
>> ___OUTPUT___:
>> ![[Pasted image 20240330183337.png]]


