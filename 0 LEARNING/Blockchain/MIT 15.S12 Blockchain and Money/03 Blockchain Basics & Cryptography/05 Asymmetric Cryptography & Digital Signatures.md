---
topic: blockchain
---
## Digital Signature Algorithms
- ___General Key Pair___ - Public Key (PK) & Private Key (SK) - from random number
- ___Signature___ - Creates ___Digital Signature___ ( ___Sig___ ) from _message_ ( _m_ ) and __Private Key__ ( __sk__ )
- ___Verification___ - Verifies if a ___Signature___ ( ___Sig___ ) is valid for a _message_ ( _m_ ) and a __Public Key__ ( __PK__ )

## Properties
- Infeasible to find __Private Key ( SK )__ from ___Public Key ( PK )___
- All valid signatures verify
- Signatures infeasible to forge

## Bitcoin Digital Signature Function
- Elliptic Curve Digital Signature Algorithm (EDCSA) ... y2 = x3 + 7

![[Pasted image 20230924075702.png]]
![[Pasted image 20230924075720.png]]