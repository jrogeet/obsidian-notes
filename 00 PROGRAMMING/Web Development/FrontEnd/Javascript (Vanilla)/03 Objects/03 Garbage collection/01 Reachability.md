---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #object
∗:[[01 Javascript|JavaScript]] 

---
# Reachability

--- 
The main concept of _memory management_ in JavaScript is ___reachability___.

"__Reachable__" values are those  that are accessible or usable somehow.
They are guaranteed to be stored in memory.
>[!Info] __Roots__
> __Roots__ are set of inherently reachable values, that ___cannot be deleted___:
> - Currently executing function, its local variables and parameters.
> - Other function on the current chain of nested calls, their local variables and parameters.
> - Global variables
> - (there are some other, internal ones as well)

Any other values is _considered reachable_ if it's reachable from a __root by reference or by a chain of references__.
>[!example]- 
>If there's an `object` in a global variable,
>and that `object` has a __property__ ___referencing another___ `object`,
>that `object` is considered _reachable_.
>And those __it references__ are also _reachable_.

---
>[!example]
>```javascript
>// user has a reference to the object
>let user = {
>	name: "John"
>};
>```
>![[Pasted image 20240117160540.png]]
>If the values of `user` is __overwritten__, the reference is ___lost___:
>```javascript
>user = null;
>```
>![[Pasted image 20240117160646.png]]
>The object becomes unreachable. Garbage collector will junk the data and free the memory.
>
> ## Two References
> The object is still reachable via `admin` global variable.
> ```javascript
> // user has a reference to the object
> let user = {
> 	name: "John"
> };
> 
> let admin = user;
> ```
> ![[Pasted image 20240117160904.png]]
> ```javascript
> user = null;
> ```
> If `admin` is also overwritten, then it will be removed.
> 
> ## Interlinked objects
> The `marry` function "__marries__" two `objects` by giving them references to each other and returns a new `object` that _contains them both_.
> ```javascript
> function marry(man, woman) {
> 	woman.husband = man;
> 	man.wife = woman;
> 	
> 	return {
> 		father: man,
> 		mother: woman
> 	}
> }
> 
> let family = marry({
> 	name: "John"
> }, {
> 	name: "Ann"
> });
> ```
> ![[Pasted image 20240117194308.png]]
>>[!Danger] Removing two references:
>> ```javascript
>> delete family.father;
>> delete family.mother.husband;
>> ```
>> ![[Pasted image 20240117200046.png]]
>> ___Outgoing references___ do not matter.
>> Only __incoming__ ones can make an object _reachable_. 
>> ![[Pasted image 20240117200541.png]]
>> After garbage collection:
>> ![[Pasted image 20240117201922.png]]
>
> ## Unreachable island
> ```javascript
> family = null;
> ```
> ![[Pasted image 20240117202413.png]]
> John and Ann still linked (both have incoming references)
> But `family` object has been unlinked from the root, no reference to it any more, so the whole island becomes unreachable and will be removed.
> 

READ MORE:
INTERNAL ALGORITHMS - https://javascript.info/garbage-collection#internal-algorithms
 



