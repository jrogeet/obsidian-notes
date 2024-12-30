---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #switch
∗:[[01 Javascript|JavaScript]] 

---
# 01 Switch statement

--- 
`switch` statement can replace multiple `if` checks.

>[!Abstract] Syntax:
>`switch` has one or more `case` and an optional default.
>```javascript
>switch(x) {
>	case 'value1': // if (x === 'value1')
>		...
>		[break]
>				
>	case 'value2': // if (x === 'value2')
>		...
>		[break]
>	default:
>		...
>		[break]
>}
>```
> - `x` is checked for strict equality with `case` (`value1`), then to the second (`value2`) and so on.
> - If equality is found, `switch` execute the code _from the corresponding_ `case`, until __nearest__ `break` (___or until the end of___ `switch`)  
> - __If NO CASE is MATCHED__ then `default` code is executed (_if it exists_).

>[!Example]
>```Javascript
>let a = 2 + 2; 
>
>switch  (a) {
>	case 3:
>		alert( 'Too small' );
>		break;
>	case 4:
>		alert( 'Exactly!' );
>		break;
>	default:
>		alert( "I don't know such values" );
>}
>```
>- `switch` starts to compare `a` with 1st `case` variant `3`, Match __Fails__
>- Then `4`, a match, execution starts from `case 4` until the nearest bank

If there's no `break` the execution continue with the next `case` without any checks.

Example without `break`:
```javascript
let a = 2 + 2;

switch(a) {
	case 3:
		alert( 'Too small' );
	case 4:
		alert('Exactly!');
	case 5:
		alert( 'Too big' );
	default:
		alert( "I don't know such values" );
}
```

>[!tip] Any expression can be `switch/case` argument
>Both `switch` and `case` allow arbitrary expressions.
>For example:
>```javascript
>let a = "1";
>let b = 0;
>
>switch (+a) {
>	case b + 1;
>		alert("this runs, because +a is 1, exactly equals b+1");
>		break;
>		
>	default:
>		alert("this doesn't run");
>}
>```
>- `+a` gives `1`
>- compared to `b + 1` in `case`




