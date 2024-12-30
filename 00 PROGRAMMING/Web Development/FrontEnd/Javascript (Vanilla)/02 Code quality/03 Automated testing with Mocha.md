---
topic: javascript
---
Tags/Topics: #javascript #jsbasics 
∗:[[01 Javascript|JavaScript]] 

---
# Automated testing with Mocha.js

--- 
**Automated testing means that tests are written separately, in addition to the code. They run our functions in various ways and compare results with the expected.**

>[!info]- Behavior Driven Development ( BDD )
> # Behavior Driven Development (BDD)
> __BDD__ is three things in one:
> - tests AND
> - documentation AND
> - examples.


## Specification or spec
For example, we create a function `pow(x, n)` which raises `x` to an integer power `n`.
```javascript
describe("pow", function() {
	
	it("raises to n-th power", function() {
		assert.equal(pow(2, 3), 8);
	});
});
```

A spec has three main building blocks:
- `describe("title", function() { ... })`
	- What functionality we're describing?
		- In this case, we're describing the function `pow`. Used to group "workers" -- the `it` blocks.
- `it("use case description", function() { ... })`
	- Describe in _human-readable_ way the use case
	- Second argument is a function that tests it.
- `assert.equal(value1, value2)`
	- The code inside `it` block, if implementation is correct, should execute without errors.
	- Functions `assert.*` check whether `pow` or the function works as expected.
		- `assert.equal` _compares arguments and yields an error if they are not equal_.
			- here it checks `pow(2, 3)` equals `8`

>[!check] The development flow
>The flow of development usually looks like this:
>1. An initial spec is written, with tests for the most basic functionality.
>2. An initial implementation is created.
>3. To check whether it works, we run the testing framework _Mocha_ that runs the spec. While the functionality is not complete, errors are displayed. We make corrections until everything works.
>4. Now we have a working initial implementation with tests.
>5. We add more use cases to the spec, probably not yet supported by the implementations.
>	Tests start to fail.
>6. Go to 3, update the implementation till tests give no errors.
>7. Repeat  steps 3-6 till the functionality is ready.
>
>So, the development is iterative. We write the spec, implement it, make sure tests pass, then write more tests, make sure they work etc. At the end we have both a working implementation and tests for it.


## Spec in action
>[!example] Some JavaScript libraries for tests:
> - __Mocha__ - provides  common testing functions including `describe` and `it` and the main function that runs tests.
> - __Chai__ - the library with many assertions. Allows use of a lot of different assertions.
> - __Sinon__ - a library to _spy over functions_, emulate built-in functions and more.
> 
> ![[Pasted image 20240111132706.png]]
> 1. `<head>` add third-party libraries and styles for tests.
> 2. `<script>` with the function to test, in our case - with the code for `pow`
> 3. The tests - in our case an external script `test.js` that has `describe("pow", ...)` from above.
> 4. The HTML element `<div id="mocha">` will be used by Mocha to output results.
> 5. The tests are started by the command `mocha.run()`
>


>[!example] 2 Ways to organize tests:
>1. Add one more `assert` into the same `it`:
>```javascript
>describe("pow", function() {
>	
>	it("raises to n-th power", function() {
>		assert.equal(pow(2, 3), 8);
>		assert.equal(pow(3, 4), 81);
>	});
>});
>```
>
>2. Make TWO tests:
>```javascript
>describe("pow", function() {
>	it("2 raised to power 3 is 8", function() {
>		assert.equal(pow(2, 3), 8);
>	});
>	it("3 raised to power 4 is 81", function() {
>		assert.equal(pow(3, 4), 81);
>	});
>});
>```
>When `assert` triggers an error, the `it` block __immediately terminates__.
>	- In the _first_ variant if the first `assert` fails, the _second_ `assert` will not run.
>	- ![[Pasted image 20240111175157.png]]
>The _second_ variant is __better__.
>- Good to follow rule:
>	- __One test checks one thing.__


>[!Example]
>```javascript
>function pow(x, n) {
>	let result = 1;
>	
>	for (let i = 0; i < n; i++) {
>		result *= x
>	}
>	
>	return result;
>}
>```
>Instead of writing `it` blocks manually, we can generate them in `for`:
>```javascript
>describe("pow", function() {
>	function makeTest(x) {
>		let expected = x * x * x;
>		it(`${x} in the power 3 is ${expected}`, function() {
>			assert.equal(pow(x, 3), expected);
>		});
>	}
>	
>	for (let x = 1; x <= 5; x++) {
>		makeTest(x);
>	}
>	
>});
>```

### Nested Describe
```javascript
describe("pow", function() {
	
	describe("raises x to power 3", function() {
		function makeTest(x) {
			let expected = x * x * x;
			it(`${x} in the power 3 is ${expected}`, function() {
			}); 
		}
		
		for (let x = 1; x <= 5; x++) {
			makeTest(x);
		}
	});
	
	// ... more tests to follow here, both describe and it can be added
})
```

### before/after and beforeEach/afterEach

>[!info] `before/after` and `beforeEach/afterEach`
>- `before/after` functions execute before/after running tests
>- `beforeEach/afterEach` functions that execute before/after every `it`.
>```javascripts
>describe("test", function() {
>	
>	before(() => alert("Testing started - before all tests"));
>	after(() => alert("Testing finished - after all tests"));
>	
>	beforeEach(() => alert("Before a test - enter a test"));
>	afterEach(() = > alert("After a test - exit a test"));
>	
>	it('test 1', () = alert(1));
>	it('test 2' () => alert(2));
>});
>```
>
>The running sequence will be:
>```text
>Testing started - before all tests (before)
>Before a test - enter a test (beforeEach)
>1
>After a test - exit a test (afterEach)
>Before a test - enter a test (beforeEach)
>2
>After a test - exit a test (afterEach)
>Testing finished - after all tests (after)
>```
>
>`beforeEach/afterEach` and `before/after` are used for initialization, zero out corners or do something else between the tests (or test groups).

### Other assertions:
>[!example] Other assertions:
>- `assert.isNaN`: checks for `NaN`
>```javascript
>describe("pow", function() {
>	
>	// ...
>	
>	it("for negative n the result is NaN", function () {
>		assert.isNaN(pow(2, -1));
>	});
>	
>	it("for non-integer n the result is NaN", function () {
>		assert.isNaN(pow(2, 1.5));
>	});
>});
>```
>Add a couple lines to `pow`:
>```javascript
>function pow(x, n) {
>	if (n < 0) return NaN;
>	if (Math.round(n) != n) return NaN;
>	
>	let result = 1;
>	
>	for (let i = 0; i < n; i++) {
>		result *= x;
>	}
>	
>	return result;
>}
>```
>![[Pasted image 20240111234611.png]]
>- `assert.equal(value1, value2)` - checks the equality `value1 == value2`
>- `assert.strictEqual(value1, value2)` - checks the strict equality `value1 === value2`
>- `assert.notEqual`, `assert.notStrictEqual` - inverse checks to the ones above.
>- `assert.isTrue(value)` - checks that `value === true`
>- `assert.isFalse(value)` - checks that `value === false`
>- etc... https://www.chaijs.com/api/assert/
