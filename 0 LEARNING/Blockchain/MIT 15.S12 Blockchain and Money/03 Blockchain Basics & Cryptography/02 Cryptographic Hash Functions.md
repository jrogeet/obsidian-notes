---
topic: blockchain
---
__"Digital Fingerprints ![[Pasted image 20230924075532.png]]
## General Properties

- Maps input ___X___ of __any size__ to an Output of __fixed size__ - called a ___Hash___
- __Deterministic__: Always the __same Hash__ for the same ___X___
	- A __set of Data__ will always give the same ___Hash___.
- Efficiently computed

## Cryptographic Properties

- ___PREIMAGE RESISTANT (One Way)___: _infeasible_ to determine ___X___ from __Hash(X)__
	- It's ___infeasible___ to determine the __Input___ using the ___Output___.
	- It's ___infeasible___ to determine the ___X___ from the __Hash__ of ___X___

- ___COLLISION RESISTANT :___ infeasible to find and ___X___ and ___Y___ where __Hash__( ___X___ ) = __Hash__( ___Y___ )

- ___AVALANCHE EFFECT___ : Change ___X___ slightly and __Hash__ ( ___X___ ) changes significantly
	- Change something a little different and the rest looks different.
		- This is important because it makes it more secure

- ___PUZZLE FRIENDLINESS___ : Knowing __Hash__ ( ___X___ ) and part of ___X___ it is still very hard to find rest of ___X___
	- Even if you know a little bit of the input doesn't mean you'll get the output


## Uses as
- Names
- References
- Pointers
- Commitments

## Bitcoin Hash Functions
- Headers & Merkle Trees - SHA 256
- Bitcoin Addresses - SHA 256 and RIPEMD160