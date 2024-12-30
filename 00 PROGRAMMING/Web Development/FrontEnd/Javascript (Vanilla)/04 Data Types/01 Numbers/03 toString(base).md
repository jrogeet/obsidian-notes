---
topic: javascript
---
Tags/Topics: #javascript #jsbasics 
∗:[[01 Javascript|JavaScript]] 

---
# toString(base)

--- 

> [!abstract]
> method `num.toString(base)` returns a __string representation__ of `num` in the numeral system with the given `base`.
> ```javascript
> let num = 255;
> 
> alert( num.toString(16) ); // ff
> alert( num.toString(2) ); // 11111111
> ```
> `base` can vary from `2` to `36`
> By default it's `10`
> 
>> [!tip] Common use cases:
>> - `base = 16` used for __hex colors__, __character encodings__ etc, digits can be `0..9` or `A..F`
>> - `base = 2` mostly for __debugging bitwise operations__, digits can be `0` or `1`
>> - `base = 36` __the maximum__, digits can be `0..9` or `A..Z`.
>> 	- Useful case: Turning a __long numeric identifier__ into something shorter.
>> 		- For Example: Make a ___Short URL___.
>>
>>> [!example] `base = 36` Example
>>>```javascript
>>>alert( 123456..toString(36) ); // 2n9c
>>>```

>[!tip] 2 dots e.g. `..toString()`
>To call a method __directly on a number__, like `toString` then we __need to place two dots__ `..` after it.
>
>Placing a ___single dot___ would cause an error: `123456.toString(36)`
>	JavaScript implies the ___decimal part___ after the ___first dot___.
>
>So, __if we place more dots__, JavaScript knows that the ___decimal part___ is __empty__ and now goes the __method__.
>
>Could also write `(123456).toString(36)`

