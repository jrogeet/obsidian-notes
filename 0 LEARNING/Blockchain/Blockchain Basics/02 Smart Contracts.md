
[___SOURCE___](https://www.blockchain.education/blockchain101/smart-contracts)
## History of Smart Contracts
The term “___smart contract___” was coined by American computer scientist __Nick Szabo__ in _1994_. 
Szabo described a smart contract as “_a computerized transaction protocol that executes the terms of a contract_,” 

with a general objective to “_satisfy common contractual conditions_, __minimize exceptions both malicious and accidental__, and ___minimize the need for trusted intermediaries___.”

### Bitcoin
#### 2009
The first smart contract protocol was established by bitcoin.
Conditions to be satisfied to transfer bitcoins between addresses on the network.
It includes the user signing the transaction with the correct private key that matches their public address and the user having enough funds to cover transaction fees.
#### 2012
Bitcoin upgraded the protocol to support another type of smart contract called a __multi-signature transaction__ or ___multisig___.
It requires __multiple number of addresses__ (___public keys___) to sign a transaction with their _private keys_ so the __transaction can be valid__.
> This can increase the security of funds by mitigating single points of failure, like a stolen or lost private key.
![[Pasted image 20231004163017.png | 500]]

### Ethereum
#### 2013
[Ethereum Whitepaper](https://ethereum.org/en/whitepaper/)

#### 2015
Launched a new type of blockchain for __programmable smart contracts__.

Instead of the blockchain acting as effectively a _single smart contract application_ or offering a few limited opcodes,
the ___Ethereum___ blockchain offered the vision of a "world computer" capable of running numerous independent smart contracts simultaneously, distinguishing it from Bitcoin's more limited capabilities.

---

# Smart Contract
A ___smart contract___ is a tamper-proof program that runs on a blockchain network when certain predefined conditions are met.
___Smart contracts___ are self-executing computer programs that __automatically execute predefined actions when specific conditions are met__ on a blockchain.

Smart contracts are __written in code__ and _stored on a blockchain_, ensuring __transparency__ and __immutability__ of contract terms.
	Logic: “if/when __X__ event happens, then execute ___Y___ action.”
	A general notion of ___smart contracts___ could be seen in systems like __vending machine__ (e.g., a specific code leads to an expected snack)

> _One_ smart contract can have __multiple__ different conditions and _one_ application can have __multiple__ different smart contracts to support an interconnected set of processes.

- Ethereum's ___Solidity___ is a popular programming language for smart contracts.
- Any developer can create and deploy smart contracts on a public blockchain, such as for personal yield aggregation.
- Smart contracts can involve multiple independent parties who don't necessarily trust each other, thanks to blockchain parameters.
- Smart contracts define interactions, users, timing, inputs, outputs, and more.
- They ensure multi-party digital agreements execute according to defined logic, enforced by cryptography, math, and physics.

## Examples/history of Smart Contracts
One purpose of smart contracts is to automate specific business processes between a distinct group of entities. These entities collectively come to an agreement on all a smart contract’s terms, such as payouts, process flow, and dispute resolutions. A simple smart contract example for global trade may have terms like:

- ___Term 1___: If the goods arrive on time, then execute a payment from the retailer to the supplier in full amount
    
- ___Term 2___: If the goods arrive one day late, then execute a payment from the retailer to the supplier for 98% of the full amount.
    

Other smart contracts support public decentralized applications (dApps) that anyone can interact with without needing any permissions. Public dApps are often open-source so anyone in the world can inspect exactly how they function before deciding whether or not to interact with them. One example of a public dApp is a decentralized lending/borrowing market, which may have the following terms:

- ___Term 1___: If the user deposits collateral into the specific smart contract, they can receive a loan that’s up to 50% of the value of their collateral (i.e., $100 deposit can borrow up to a $50 loan).
    
- ___Term 2___: If the user’s collateralization ratio (collateral/outstanding loan value) drops below 200%, then the user’s collateral is automatically liquidated and transferred to the lenders to ensure they don’t lose money.
    
- ___Term 3___: Lenders can deposit funds into a specific contract that other users can borrow from at predefined collateralization ratios, while the lender receives a claim to a portion of the interest rate payments.
	Simplified:
	- The lenders put their money into a particular smart contract on a blockchain. This smart contract acts as a kind of digital escrow or pool for these funds.
	- Other users can borrow from this pool of funds but need to provide collateral.
	- As borrowers repay their loans with interest, the lenders receive a portion of those interest payments as a return on their deposited funds.

## Benefits
Most __traditional digital agreements__ involve two parties that don’t know each other, introducing the risk that _either participant won’t uphold their commitments_.
	To resolve counterparty risk, 
		Digital agreements are often hosted and executed by larger, centralized institutions like banks, which can enforce the contract’s terms.
		These digital contracts can be directly between: 
			- a _user_ and a __large company__ or 
			- involve a __large company__ acting as a trusted intermediary between _two users_.
			. 
	While this dynamic allows many contracts to exist that otherwise wouldn’t because parties might not be willing to take on risk, 
	it also creates a situation where the __larger__, centralized institutions _exert asymmetrical influence_ over agreements.
	![[Pasted image 20231004185532.png]]

Smart contracts offer several advantages over traditional digital agreements.

- ___Security___ — Running a contract on a decentralized blockchain ensures that 
	- there is _no central point of failure_, 
	- no centralized __intermediary__ to bribe, and 
	- no mechanism for either party or a central administrator to leverage to _tamper with the outcome_.
	    
- ___Reliability___ — Having the contract logic redundantly processed and verified by a decentralized network of nodes provides strong guarantees that the contract will __execute on time according to its terms__.
    
- ___Equity___ — Using a decentralized network to host and enforce the terms of an agreement reduces the ability of a middle party to use their position of privilege to rent-seek and siphon off value.
    
- ___Efficiency___ — Automating the backend processes of the agreement—escrow, maintenance, execution, and/or settlement—means neither party has to wait for manual data to be entered, the counterparty to fulfill their obligations, or a middle party to process the transaction.












> [!SUMMARY]
> Content

