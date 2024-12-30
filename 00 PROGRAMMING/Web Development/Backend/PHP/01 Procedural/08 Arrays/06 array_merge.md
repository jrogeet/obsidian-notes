---
topic: php
---


Tags/Topics: #php #array
∗:[[0 PHP|PHP]]

---
# Design

--- 
> [!info] 
> Merge multiple arrays
> - If `arrays` have __THE SAME NUMBERIC `keys`__ 
> 	- they will be __APPENDED__
> - `keys` will be __RE-ORDERED__
> ```php 
> $array1 = [1, 2, 3];
>  $array2 = [6 => 4, 7 => 5, 8 => 6];
>   $array1 = [7, 8, 9];
>   
>$merged = array_merge($array1, $array2, $array3); // 1, 2, 3, 4, 5, 6, 7, 8, 9
> ```
> 
>> [!tip] Overwriting
>> ```php
>> $array1 = [1, 2, 3];
>>  $array2 = ['a' => 4, 'b' => 5, 'c' => 6];
>>   $array1 = [7, 8, 9, 'b' => 10];
>>   
>>   $merged = array_merge($array1, $array2, $array3); // 1, 2, 3, [a] => 4, [b] => 10, [c] => 7, 8, 9
>> ```

