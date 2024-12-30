---
topic: php
---


Tags/Topics: #php #array
∗:[[0 PHP|PHP]]

---
# Design

--- 
 >[!info]
 >Finding the `key` of a certain `value`
 >- Is __Case-Sensitive__
 >```php
 >$array = ['a', 'b', 'c', 'D', 'E', 'ab', 'bc', 'cd', 'b', 'd'];
 >
 >$key = array_search('b', $array); // int(1)
 >```