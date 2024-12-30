---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 
#### Put contents to files
```php
file_put_contents('foo.txt', 'hello world');
```
If the file __DOESN'T EXIST__:
- It will __CREATE  the file__ and ___Put the content___.

> [!caution] If __File already EXISTS__:
> The contents will be __OVERWRITTEN__:
> ```php
> file_put_contents('foo.txt', 'hello'); // hello
> 
> file_put_contents('foo.txt', 'world'); // world
> ```

> [!tip] To append content:
> ```php
> file_put_contents('foo.txt', 'hello'); // hello
> 
> file_put_contents('foo.txt', 'world', FILE_APPEND); // helloworld
> ```
```
```
#### Store File Contents to Variables
```php
$content = file_get_contents('foo.txt');

$content2 = file_get_contents('foo.txt', offset: 3, length: 2)

echo $content; // hello world
echo $content2; // lo
```