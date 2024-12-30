---
topic: blockchain
---
![[Pasted image 20230923002542.png]]
## Block Header
 - ___Version ( Version Number )___
	 - A version number to track software/protocol upgrades.
 - ___Previous Block Hash___
	 - A reference to the hash of the previous (parent) block in the chain.
 - ___Merkle Root Hash___
	 - A hash of the root of the Merkle tree of this block's transactions.
	 -  A hash of all the hashes of all the transactions that are part of a block in a blockchain network.
 - ___Timestamp___
	 - The approximate creation time of this block (seconds from Unix Epoch).
 - ___Difficulty Target___
	 - The proof-of-work algorithm difficulty target for this block.
 - ___Nonce___
	 - A counter used for the proof-of-work algorithm, making the serialized header format part of the consensus rules.

