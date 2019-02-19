# Frequently Asked Questions

### 1. I'm new to RIDE and Waves Smart contracts, is there any tutorial or articles to start with?

Yes sure, you can check [_**Video Tutorials and Articles**_](/smart-contracts/video-tutorials-and-articles.md) section.

### 2. Is smart contract functionality added in Waves ? If Yes, which languages are supported?

Yes, Waves has its own language for Smart Contracts. It is called [_**RIDE**_](/smart-contracts/ride-language/ride-language.md).

### 3. Is it possible to convert an existing token to a smart token via a script, or must you implement a token swap?

Yes by using [_**smart assets**_](/smart-contracts/smart-assets.md) concept.

### 4. I don't know about account scripts. Do you know where I could find appropriate documentation?

The best is to start with [_**as a developer guide.                        
**_](/getting-started/as-a-developer.md)

### 5. How many Tx does waves have? will SC add another transaction type to the wavesplatform? Where can I find a valid SetScript transaction from testnet?

There are [_**14 tx types**_](/waves-api-and-sdk/waves-node-rest-api/example-transactions.md) on Waves and publishing a script for an account is one of those \(type 13 SetScript Tx\).

### 6. Does Waves smart contracts have numbers similar Ethereum one's, 0x....?

No, but they are attached to accounts also, at least in the first version.

### 7. When you develop a dapp on Waves, is it more appropriate to have a private waves blockchain or just your own full node on the regular mainnet ?

Neither of both, you don't have to have a node for deploying a SC. Nevertheless, for the dev i would recommend to use testnet.

### 8. How can I create any interactive dApp?

[_**Smart contract**_](/smart-contracts/waves-contracts-language-description.md) on Waves can only answer 'yes' or 'no' for outgoing \(not incoming!\) transaction.

### 9. How can I get string address from tx.sender in RIDE?

```js
let senderAddress = addressFromPublicKey(tx.senderPublicKey)
or 
let senderAddress= toBase58String(addressFromPublicKey(tx.senderPublicKey).bytes)
```

### 10. What is a smart account?

The [_**smart account**_](/smart-contracts/smart-accounts.md) is an account with attached transactions checking **script**. In other words, a **script** which is attached to an account so the account can validate every transaction before confirming it.

### 11. How to calculate fees for smart accounts and smart assets?

Please check the section [_**fee calculation for smart assets**_](/smart-contracts/smart-assets.md). For each time the script is called, total transaction’s fee increases by 0.004 Waves, you can find [_**full table**_](/waves-environment/waves-protocol/transactions-fees.md) here for all transactions.

### 12. How can I get string address from tx.sender in RIDE?

```js
let senderAddress = addressFromPublicKey(tx.senderPublicKey)
or 
let senderAddress= toBase58String(addressFromPublicKey(tx.senderPublicKey).bytes)
```



