# Accounts

In Ethereum, the state is made up of objects called "accounts", with each account having a 20-byte address and state transitions being direct transfers of value and information between accounts. An Ethereum account contains four fields: 
* The nonce, a counter used to make sure each transaction can only be processed once 
* The account's current ether balance
* The account's contract code, if present
* The account's storage (empty by default)
 
In general, there are two types of accounts: externally owned accounts, controlled by private keys, and contract accounts, controlled by their contract code.

#### Externally owned accounts (EOAs)
An externally controlled account
* has an ether balance
* can send transactions (ether transfer or trigger contract code)
* is controlled by private keys
* has no associated code

#### Contract accounts
A contract 
* has an ether balance
* has associated code
* code execution is triggered by transactions or messages (calls) received from other contracts
* when executed - perform operations of arbitrary complexity (Turing completeness) - manipulate its own persistent storage, i.e., can have its own permanent state - can call other contracts.

# What is a transaction?
The term “transaction” is used in Ethereum to refer to the signed data package that stores a message to be sent from an externally owned account to another account on the blockchain.

Transactions contain:
* the recipient of the message
* a signature identifying the sender and proving their intention to send the message via the blockchain to the recipient
* `VALUE` field - The amount of wei to transfer from the sender to the recipient
* an optional data field, which can contain the message sent to a contract
* a `STARTGAS` value, representing the maximum number of computational steps the transaction execution is allowed to take
* a `GASPRICE` value, representing the fee the sender is willing to pay for gas. One unit of gas corresponds to the execution of one atomic instruction, i.e., a computational step.
 
# What is a message?
Contracts have the ability to send “messages” to other contracts. Messages are virtual objects that are never serialized and exist only in the Ethereum execution environment. They can be conceived of as function calls.

A message contains:
* the sender of the message (implicit)
* the recipient of the message
* a ``VALUE`` field - The amount of wei to transfer alongside the message to the contract address,
an optional data field, that is the actual input data to the contract
* a `STARTGAS` value, which limits the maximum amount of gas the code execution triggered by the message can incur.

# Public, private and consortium blockchains
`Public blockchains`: a public blockchain is a blockchain that anyone in the world can read, anyone in the world can send transactions to and expect to see them included if they are valid, and anyone in the world can participate in the consensus process – the process for determining what blocks get added to the chain and what the current state is. 

`Consortium blockchains`: a consortium blockchain is a blockchain where the consensus process is controlled by a pre-selected set of nodes; for example, one might imagine a consortium of 15 financial institutions, each of which operates a node and of which 10 must sign every block in order for the block to be valid. The right to read the blockchain may be public, or restricted to the participants, and there are also hybrid routes.

`Private blockchains`: a fully private blockchain is a blockchain where write permissions are kept centralized to one organization. Read permissions may be public or restricted to an arbitrary extent.


# Mining in Ethereum 

Ethereum, like all blockchain technologies, uses an incentive-driven model of security. Consensus is based on choosing the block with the highest total difficulty. Miners produce blocks which the others check for validity. Among other well-formedness criteria, a block is only valid if it contains proof of work (PoW) of a given difficulty. 

The Ethereum blockchain is in many ways similar to the Bitcoin blockchain, although it does have some differences. The main difference between Ethereum and Bitcoin with regard to the blockchain architecture is that, unlike Bitcoin, Ethereum blocks contain a copy of both the transaction list and the most recent state (the root hash of the merkle patricia trie encoding the state to be more precise). Aside from that, two other values, the block number and the difficulty, are also stored in the block. 

The proof of work algorithm used is called Ethash (a modified version of the Dagger-Hashimoto algorithm) and involves finding a nonce input to the algorithm so that the result is below a certain difficulty threshold. The point in PoW algorithms is that there is no better strategy to find such a nonce than enumerating the possibilities, while verification of a solution is trivial and cheap. Since outputs have a uniform distribution (as they are the result of the application of a hash function), we can guarantee that, on average, the time needed to find such a nonce depends on the difficulty threshold. This makes it possible to control the time of finding a new block just by manipulating the difficulty. 

# Links
[https://github.com/ethereum/wiki/wiki/White-Paper ]

[http://www.ethdocs.org/  ]
