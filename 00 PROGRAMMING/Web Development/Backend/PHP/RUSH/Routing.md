---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 

>[!tip] `parse_url`
>```php
>parse_url($_SERVER['REQUEST_URI']);
>parse_url($_SERVER['REQUEST_URI'])['path'];
>```
> - Separates the `path` to the `query`
> Example: `website/contact?name=foo`
> - `/contact` is the __path__
> - `?name=foo` is the ___query___
> 	- It creates an `object` with `path` as key of the __path__
> 		- and `query` as the key of the ___query___



> [!example]
> ```php
> $uri = parse_url($_SERVER['REQUEST_URI'])['path'];
> 
> if ($uri === '/') {
> 	require 'controllers/index.php';
> } elif ($uri === '/about') {
> 	require 'controllers/about.php';
> } elif ($uri === '/contact') {
> 	require 'controllers/contact.php';
> }
> ```
> Better version:
> ```php
> $uri = parse_url($_SERVER['REQUEST_URI'])['path'];
> 
> $routes = [
> 	'/' => 'controllers/index.php',
> 	'/about' => 'controllers/about.php',
> 	'/contact' => 'controllers/contact.php',
> ];
> 
> function abort($code = 404) { // Default value
> 	http_response_code($code);
> 	
> 	require "views/{$code}.php";
> 	
> 	die();
> }
> 
> if (array_key_exists($uri, $routes)) {
> 	require $routes[$uri]
> } else {
> 	abort();
> }
> ```
