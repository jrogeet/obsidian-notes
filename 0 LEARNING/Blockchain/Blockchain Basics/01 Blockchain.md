---
Topic: Blockchain
Author: 
Type: 
banner: obsidian://open?vault=Obsidian%20Vault&file=0%20LEARNING%2FBlockchain%2FBlockchain%20Basics%2Fattachments%2Fblockchain.webp
---
Link: []()

---
>[!INFO]- Definition
>- A blockchain is a decentralized and distributed digital ledger technology that records transactions across a network of computers in a secure and immutable manner. 
>- It enables transparent and tamper-resistant record-keeping without the need for a central authority.

>[!Example]- Terms
> __Hash__ - Unique fixed length string meant to identify a piece of data
> __Hash Function/Algorithm__ - A function that computes data into a unique hash
> __Mining__ - The process of finding the "___solution___" to the blockchain "___problem___"
> - Example: the "___problem___" was to find a hash that starts with four zeros.
> - _Nodes_ get paid for mining blocks
> 
> __Block__ - A list of transactions mined together
> __Decentralized__ - Having no single point of authority
> __Private Key__ - Only known to the key holder, it's used to "sign" transactions
> __Public Key__ - derived from your __Private Key__. Anyone can "see" it, and use it to verify that a transaction came from you.
> __Node__ - A single instance in a decentralized network


Blockchain is a database/ledger where you can store any type of data, and make it immutable.
- Different from a typical database, the way it stores information.
- Data is immutable / irreversible / cannot be altered
- The blocks are linked/chained together via cryptography
	- If you alter a single thing in a block all the next block would be invalid.

>[!caution] Changing data
>The only way to change a data or information is upon the user or program entering them.
## How does Blockchain store data?

- Once data has been entered, the system will put it inside a block
- A block's data capacity is limited
- Once a block's capacity is full, all the data gets processed through a __Cryptographic hash function__ to create the block's ___Hash___.
- Then, a new block will be created containing the ___Hash___ of the previous block.
	- This is what makes them chained together.


### How do Blockchain Networks Process __Transactions__ ?
Transactions on different blockchains follow specific processes depending on the blockchain's design.
>[!info]- In bitcoin:
>![[Pasted image 20231006131051.png]]
> - Transactions are stored in a "memory pool" and queued until a miner validated it.
> - Then, added to a block until the block's capacity is full of transactions, closed and encrypted.
> - 

>[!info] Proof-of-Work
> - Miners compete to solve or find a valid nonce (number only used once)
> - After finding a valid nonce the miner sends or broadcast it to the whole network
> - Other miners, check and validate if it's a valid hash
> - If correct, the new block of transactions will be validated and check and verify it's transaction if there's no double-spending that happened
> - The miner that solved the PoW puzzle is rewarded with Cryptocurrency as well as transaction fees from the block

## Blockchain Decentralization
- All the nodes or computers that is running blockchain have their own copy of the database
- The distribution of the database and the Proof-of-Work(PoW) makes the data irreversible.
>[!info]
>the data in a database isn't limited to transaction, it could be like legal contracts, state identifications, votes in an election, company's product inventory, etc..



### Transparency & Security
- Everybody has a copy of the chain, they can see all the new blocks that being added to the blockchain on their own node or computer.
	- There is also [Blockchain Explorers](https://www.blockchain.com/explorer?utm_campaign=dcomnav_explorer) where you can see live transactions from a blockchain.
>[!example] In bitcoin you can track where a certain bitcoin goes.
>Exchanges have been hacked a lot of cryptocurrency before, 
>We might not know who they are, but we know their wallet address and the address of the bitcoin they hacked

>[!Danger] Is Blockchain Secure?
>- New blocks are stored at the end of the blockchain, linearly and chronologically
>- Previous block, cannot be changed
>- Each block contains previous block's hash
>	- The network will reject an altered block since the next blocks would not match
>>[!caution]+ Not all blockchains are 100% impenetrable
>>If a hacker wants to alter a blockchain and steal cryptocurrencies, the hacker need to have a __computational power of 51% of all the nodes__ in that blockchain.
>>- This is also known as the ___51% attack___
>>	- In this attack, Timing is Everything.

>[!important]+ Benefits and Drawbacks of Blockchain
>
>|Pros|Cons|
>|----|----|
>| - Improved accuracy by removing human involvement in verification<br><br>- Cost reductions by eliminating third-party verification<br><br>- Decentralization makes it harder to tamper with<br><br>- Transactions are secure, private, and efficient<br><br>- Transparent technology<br><br>- Provides a banking alternative and a way to secure personal information for citizens of countries with unstable or underdeveloped governments|-Significant technology cost associated with some blockchains<br><br>- Low transactions per second<br><br>- History of use in illicit activities, such as on the dark web<br><br>- Regulation varies by jurisdiction and remains uncertain<br><br>- Data storage limitations |



## Hash, Block and Blockchain
### Hash
![[Pasted image 20231008194740.png | 500 ]]
- Hashing returns a fixed-length unique string of characters
- No matter how long the data is, the function will return fixed-length hash code
- ___SHA256___ hash function always returns __64__-bits of characters

### Block
![[Pasted image 20231008200523.png| 400]]
- The Hash of a block are based from the __Block Number__ + _Nonce_ + ___Data___.
- Miners use computational power to solve the Nonce that will return a Hash that starts with certain amount of zeros![[Pasted image 20231008201431.png | 373]]
	- For example here, if the Hash starts with 4 Zeros

### Blockchain
>[!important] Blockchain
>- In a blockchain, the First Block is called the ___Genesis Block___
>- Each block will contain the ___Hash___ of the __Previous Block__
> ![[Pasted image 20231008203414.png]]
>  ![[Pasted image 20231008203446.png | 600]]
>   ![[Pasted image 20231008203501.png | 300]]
>   - Tampering/Altering a data from a block would result to all the next block being invalid.
> 	  - When a single data



### Private & Public Keys
A Private key is paired with a Public key
- Public Key is what the whole world see
	![[Pasted image 20231008212707.png | 400]]
- Private Key is used to digitally sign transactions
- Public Key is what everyone use to verify that it is you that signed the transaction
	
Similar to hashing, but instead of Hash Function/Algorithm it uses _Elliptic Curve Digital Signature Algorithm_ (__ECDSA__)
	![[Pasted image 20231008213403.png | 400]]

#### Transactions
![[Pasted image 20231008213705.png | 450]]
![[Pasted image 20231008213729.png |450]]

