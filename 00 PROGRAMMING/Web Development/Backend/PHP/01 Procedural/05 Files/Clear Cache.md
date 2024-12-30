---
topic: php
---


Tags/Topics: #php #files
∗:[[0 PHP|PHP]]

---
# Design

---


#### Clear cache values of `functions` like `filesize`
```php
echo filesize('foo.txt');

file_put_contents('foo.txt', 'hello world');
clearstatcache();

echo filesize('foo.txt');
```

