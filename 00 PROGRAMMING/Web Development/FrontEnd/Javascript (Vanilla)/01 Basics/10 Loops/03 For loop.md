---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #loops 
∗:[[01 Javascript|JavaScript]] 

---
# 03 For loop

--- 
Syntax:
```javascript
for (begin; condition; step) {
	// ... loop body ...
}
```

This loop runs `alert(i)` for `i` from `0` up to (_but not including_) `3`:
```javascript
for (let i = 0; i < 3; i++) { // shows 0, then 1, then 2
	alert(i);
}
```

Let’s examine the `for` statement part-by-part:

| part      |             |                                                          |
| --------- | ----------- | -------------------------------------------------------------- |
| begin     | `let i = 0` | Executes once upon entering the loop                           |
| condition | `i < 3`     | Checked before every loop iteration. If false, the loop stops. |
| body      | `alert(i)`  | Runs again and again while the condition is truthy.            |
| step      | `i++`       | Executes after the body on each iteration|

>[!INFO] General Loop algorithm works like this:
>Run begin
> -> (if condition -> run _body_ and run __step__)
> -> (if condition -> run _body_ and run __step__)
> -> (if condition -> run _body_ and run __step__)
> -> ...

```javascript
// for (let i = 0; i < 3; i++) alert(i)

//run begin
let i = 0
// if condition -> run body and run step
if (i < 3) { alert(i); i++}
// if condition -> run body and run step
if (i < 3) { alert(i); i++}
// if condition -> run body and run step
if (i < 3) { alert(i); i++}
// ... finish, because now i == 3
```

>[!TIP] Inline variable declaration
>"_counter_" variable `i` is declared right in the loop.
>```javascript
>for (let i = 0; i < 3; i++) {
>	alert(i); // 0, 1, 2
>}
>alert(i); // error, no such variable
>```
>Instead of defining a variable, we could use an existing one:
>```javascript
>let i = 0;
>
>for (i = 0; i < 3; i++) { // use an existing variable
>	alert(i); // 0, 1, 2
>}
>
>alert(i); // 3, visible, because declared outside of the loop
>```

### Skipping parts
Any part of `for` can be skipped.

We can omit `begin`
- If we don't need to do anything at the __loop start__
```javascript
let i = 0; // `i` already declared and assigned
for (; i < 3; i++) { // no need for "begin"
	alert( i ); // 0, 1, 2
}
```

and the `step`
- making it identical to `while (i < 3)`
```javascript
let i = 0;

for (; i < 3;) {
	alert(i++);
}
```

Remove everything for _infinite loop_:
- two `for` semicolons `;` must be present.
	- otherwise, ___Syntax error___
```javascript
for (;;) {
	// repeats without limits
}
```

---
Output _even_ numbers `2` to `10`
```javascript
for (let i = 2; i <= 10; i++) {
	if (i % 2 == 0) {
		alert( i );
	}
}
```

---
Both outputs `0` to `4`:
```javascript
for (let i = 0; i < 5; ++i) alert( i );

for (let i = 0; i < 5; i++) alert( i );

```
- Execute once `i = 0` before everything (begin)
- Check the condition `i < 5`
- If `true` - execute the loop body `alert(i)`
- and then `i++`
	- The value returned by increment isn't used
		- There's no difference between `i++` and `++i` here.