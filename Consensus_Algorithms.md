# Types of nodes
There are two types of nodes in classic blockchain network:
* full nodes
* light nodes

Nodes are not necessarily wallets! You can have a wallet without operating a node!

Full nodes store the whole history of transactions and can re-validate the verified block if there is an invalid transaction there.

Light nodes don't store the whole blockchain, they can have it partly or not have at all. They can only validate transactions, but not allowed to create blocks.
Ethereum definition:
>A client program that allows users in low-capacity environments to still be able to execute and check the execution of transactions without needing to run a full Ethereum node (Geth).

If you want to be a miner, you should better have a full node.

# Proof-of-Stake for Dummies

To become a miner in PoS Blockchain network, you have to prove you have enaugh tokens (coins whatever) to mine (verify) the block. You decide how many tokens you are ready to give (deposit) to compete with other miners. Consider we have 10 possible miners. The network randomly choose the winner, who is then allowed to create a block. All other nodes just validate the transactions (as in PoW network) in order to prove their correctness. If you build the right block without invalid transactions, you add it to the blockchain and get your deposit back. If you verify the block with invalid transactions, you don't receive your coins back. You don´t need nonce in PoS an nobody competes to mine the block. 

###  Delegated PoS
Basic concept: you are miner and your friends want to help you win the competition for verifying blocks. They give their coins to you (credit), so that you have the bigger stake. If you win, you give money back with some extra rewards.

# PoW in Ethereum
Interestin fact: if two miners mine the block in the same time, but as you know just one of them can be added to blockchain, the looser receive some payback, as he also spent some resources to verify the block. 

# Practical Byzantine Fault Tolerance 
All participants in the network possess known identities (you know who is who). The algorithm presumes the majority of participants are good (not corrupt). If the majority validates the block, it is considered to be correct and is added to the blokchain. If you are suspicious, you can always prove transactions yourself. If bad guys unite and create a majority, it is definitely not good for you :)

# PoW vs PoS

| PoW        | PoS           |
| :-------------: |:-------------:|
| More centralized as the biggest richest farms win      | More decentralized, less costs |
| Nonce (some number to create new hashes)      | No nonce      |
| But forks are easy to handle as the longest chain always wins | Forks are problem, it is possible you have more valid blockchain versions      |
| Electricity:)       | The other question is where stake goes if you verified the invalid block - pain point of PoS     |

# Public vs Private Blockchain
Blockchain emerged as public network. More participants you have, more secure is your network. That's why private networks are more vulnerable to attacks as you don't need much computable power to create new valid version of chain.

In public chain there is no concept for rights management. Everybody sees everything. Private blockchains try to create this privacy layer but it gives you space for corruption, as you can hide something.

Public blockchains rule!

# Links
[https://github.com/ethereum/wiki/wiki/Proof-of-Stake-FAQ]
