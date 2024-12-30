---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 
> [!info] `__isset()`
> ```php
> public function __isset(string $name): bool
> {
> 	return array_key_exists($name, $this->data);
> }
> ```
> - Its purpose is to determine if the specified property (`$name`) exists within the object and has a value that's not `null`.

>[!info] `__unset()`
> ```php
> public function __isset(string $name): void
> {
> 	unset($this->data[$name]);
> }
> ```
