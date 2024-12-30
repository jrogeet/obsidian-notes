---
topic: javascript
---
Tags/Topics: #javascript #jsbasics 
∗:[[01 Javascript|JavaScript]] 

---
# Methods in constructor

--- 


For instance, `new User(name)` below creates an object with the given `name` and the method `sayHi`:
```javascript
function User(name) {
	this.name = name;

	this.sayHi = function() {
		alert("My name is: " + this.name);
	};
}

let john = new User("John");

john.sayHi(); // My name is: John

/*
john = {
	name: "John",
	sayHi: function() { ... }
}
*/
```

To create complex objects, there's more advanced syntax, __Classes__.

---

>[!question] Is it possible to create a function `A` and `B` so that `new A() == new B()`?
>```javascript
>function A() { ... }
>function B() { ... }
>
>let a = new A();
>let b = new B();
>
>alert( a == b ); // true
>```
>
>```javascript
>let obj = {};
>
>function A() { return obj; }
>function B() { return obj;}
>
>alert( new A() == new B() ); // true
>```

>[!example] Calculator using constructors
>```javascript
>function Calculator() {
>	
>	this.read = function() {
>		this.a = +prompt('a?', 0);
>		this.b = +prompt('b?', 0);
>	};
>	
>	this.sum = function() {
>		return this.a + this.b;
>	};
>	
>	this.mul = function() {
>		return this.a * this.b;
>	};
>}
>
>let calculator = new Calculator();
>calculator.read();
>
>alert( "Sum=" + calculator.sum() );
>alert( "Mul=" + calculator.mul() );
>```

>[!example] Accumulator
>```javascript
>function Accumulator(startingValue) {
>	this.value = startingValue;
>
>	this.read = function() {
>		this.value += +prompt('How much to add?', 0);
>	};
>}
>
>let accumulator = new Accumulator(1);
>accumulator.read();
>accumulator.read();
>alert(accumulator.value);
>```
