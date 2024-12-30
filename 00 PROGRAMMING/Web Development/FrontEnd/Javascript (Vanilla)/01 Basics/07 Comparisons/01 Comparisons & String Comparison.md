---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #comparisons
∗:[[01 Javascript|JavaScript]] 

---
# 01 Comparisons & String Comparison

--- 
- ___Greater/less than___: `a > b`, `a < b`
- ___Greater/less than or equals___: `a >= b`, `a <= b`
- ___Equals___:`a == b` - __Double Equal Signs__
	- Single equal sign means assignment: `a = b`
- ___Not equals___: `a != b`

## String Comparison
To see if a string is greater than the other
JavaScript uses "dictionary" or "lexicographical" order.

```javascript
alert( 'Z' > 'A' ); // true
alert( 'Glow' > 'Glee' ); // true
alert( 'Bee' > 'Be' ); // true
```

>[!abstract]- Algorithm in comparing two strings
>- Compares the first character whether which are greater
>	- If both strings are the same, it will compare the next letters/string until the one wins
>>[!example] Glow and Glee
>>1. `G` is the same as `G`
>>2. `l` is the same as `l`
>>3. `o` is greater than `e`. Stop here. The first string is greater.

>[!Tip] Upper and lowercase letters are not equals
>`"A"` is not equal to the lowercase `"a"`
>- lowercase `"a"` is greater



