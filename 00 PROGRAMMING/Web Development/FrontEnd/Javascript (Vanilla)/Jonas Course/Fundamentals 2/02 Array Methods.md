---
topic: javascript
---
Tags/Topics: #javascript #jsbasics  #arrays 
∗:[[01 Javascript|JavaScript]] 

---
# 02 Array Methods

--- 
### Add elements

>[!tip] Push
> Adds element to the __end of an Array__
> ```javascript
> const friends = ['Michael', 'Steven', Peter];
> friends.push('Jay');
> ```
>> [!abstract] `push` returns a value
>> `push` returns the __New Length__ of the array
>> ```javascript
>> const newLength = friends.push('Jay');
>> console.log(newLength); // 4
>> ```

>[!tip] Unshift
>Adds element to the __Beginning of an Array__
>```javascript
>friends.unshift('John');
>console.log(friends);
>```

### Remove elements

>[!tip] Pop
> Removes the __last element of an Array__
>```javascript
>friends.pop()
>```
>> [!abstract] `pop` returns a value:
>> `pop` returns the __Removed element__.
>> ```javascript
>> // ["Michael", "Steven", "Peter", "Jay"];
>> 
>> const popped = friends.pop();
>> console.log(popped); // Jay
>> ```


>[!tip] Shift
>Removes the __First element of an Array__
>```javascript
>friends.shift();
>```

---
>[!tip] indexOf
>Returns the __Index number__ of an element
>```javascript
>// ["Michael", "Steven", "Peter"];
>console.log(friends.indexOf('Steven')); // 1
>```

>[!tip] includes
>Return `True` if the __element is in the Array__, and `False` otherwise.
>- Strict, number `23` does not equal `'23'`
>```javascript
>console.log(friends.includes('Steven'));
>```
>>[!example]
>>```javascript
>>if (friends.includes('Steven')) {
>>	console.log("You have a friends called Steven");
>>}
>>```


