---
topic: blockchain
---
![[Pasted image 20230924075915.png]]

![[Pasted image 20230924020250.png]]
Used the __Public Key__, Hashed it twice. 

Once with the Hash Function ___SHA256___,
Then another Hash Function ___RIPEMD-160___,
> (2 hash functions because it makes it more secure)
![[Pasted image 20230924020653.png]]

then concatenates and puts a little check sum at the end.
![[Pasted image 20230924020618.png]]

Then uses the ___Base 58___, to make it even shorter
![[Pasted image 20230924020750.png]]