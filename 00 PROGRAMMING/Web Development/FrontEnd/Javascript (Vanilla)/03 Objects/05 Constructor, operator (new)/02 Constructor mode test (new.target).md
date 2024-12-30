---
topic: javascript
---
Tags/Topics: #javascript #jsbasics 
∗:[[01 Javascript|JavaScript]] 

---
# Constructor mode test: new.target

--- 
>[!info] 
>Check whether a `function` is called with `new` with __`new.target`__ property.
>
>```javascript
>function User(){
>	alert(new.target);
>}
>
>// without "new":
>User(); // undefined
>
>// with "new":
>new User(); // function User { ... }
>```
>- Returns `undefined` for ___regular calls___
>- Equals the function if called with __`new`__.

>[!example]
>```javascript
>function User(name) {
>	if (!new.target) { // if you run me without new
>		return new User(name); // ... I will add new for you
>	}
>	
>	this.name = name;
>}
>
>let john = User("John"); // redirects call to new User
>alert(john.name) // John
>```
