---
topic: javascript
---
Tags/Topics: #javascript #jsbasics 
∗:[[01 Javascript|JavaScript]] 

---
# Polyfills and transpilers

--- 
2 tools that make modern code work on older engines (that don't understand recent features yet):
- Transpilers
- Polyfills

>[!tip] Transpilers
>Translates source code to another source code.
>It can parse("read and understand") modern code and __rewrite it using older syntax constructs__, so that it'll also work in outdated engines.
> 
>>[!example] For example:
>> __nullish coalescing operator__ `??` were released in 2020, older browsers may fail to understand the code/syntax.
>>```javascript
>>// before running the transpiler
>>height = height ?? 100;
>>
>>// after running the transpiler
>>height = (height !== undefined && height !== null) ? height : 100;
>>```

>[!tip] Polyfills
> A script that updates/adds new functions is called "__polyfill__".
> - It "__fills in__" the gap and adds missing implementations.
> 
> New language features may include _not only syntax constructs and operators_, but also __built-in functions.__
> 
>>[!example] For example:
>>`Math.trunc` doesn't exist in older/outdated JavaScript engines, and will result to failure.
>>```javascript
>>if (!Math.trunc) { // if no such function
>>	// implement it
>>	Math.trunc = function(number) {
>>		// Math.cell and Math.floor exist even in ancient JavaScript engines
>>		return number < 0 ? Math.ceil(number) : Math.floor(number);
>>	};
>>}
>>```
>
>>[!done] 2 interesting __polyfill__ libraries:
>> - (https://github.com/zloirock/core-js | core js)
>> - polyfill.io
