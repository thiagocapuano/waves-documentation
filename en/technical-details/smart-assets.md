# Smart Assets

![master](https://img.shields.io/badge/node->%3D0.15.1-4bc51d.svg)

1. [Smart Assets Definition](#smart-assets-definition)
2. [Smart Assets Features](#smart-assets-features)
3. [Smart Assets Use Cases](#smart-assets-use-cases)
4. [Smart Asset Fees](#smart-asset-fees)
5. [Trading](#trading)
6. [Validation](#validation)
7. [Examples of Scripts for Smart Assets](#examples-of-scripts-for-smart-assets)

## Smart Assets Definition

_**Smart assets**_ are unique virtual currency tokens that may represent a tangible real-world asset, or a non-tangible ownership that can be purchased, sold, or exchanged as _**defined by the rules of a script**_ on the Waves blockchain network.

In simple words, **Smart assets **are assets with an attached script which validates every transaction within that asset.

## Smart Assets Features

* **Smart assets** will allow to apply constraints on all operations for a specific asset.
* **Smart assets **will offer a great degree of autonomy, anonymity, and low-cost of transactions.

## Smart Assets Use Cases

Smart assets can be used in the following cases:

1. **Freezing assets: **It is similar to keeping the assets untouched for a particular interval of time or for a certain height, This is useful in case of having multiple funding rounds.
2. **Whitelist/blacklist:** Giving the possibility to allow/deny making a transfer for specific addresses.
3. **Taxation:** The issuer can get a share after each transaction.
4. **Multi-signature:** It's a digital signature scheme which allows a group of users to sign a transaction, It requires another user or users to sign a transaction before it can be broadcast onto the blockchain.
5. **Controlling Asset Pairs:** Tokens interchangeable with a certain currency only.
6. **Gaming:** The smart asset can be used to transfer an asset only under certain conditions \(holder has a certain attributes in a certain location\).
7. A token that indicates some commitment/debt \(unburnable, may only be transferred back with permission of the issuer\).
8. Require asset's owners to use a specific matcher.

# Smart Asset Fees

The transaction fee is calculated in the same way as for [smart accounts](/technical-details/waves-contracts-language-description/approach-and-capabilities.md): for each time the script is called, [total transaction’s fee](/technical-details/transactions-fees.md) increases by 0.004 WAVES.

**Examples:**

* If user will transfer smart assets from scripted account the final fee is 0.009.waves
* The fee for a TransferTransaction of a Smart Asset from a Smart Account would be 0.001+0.004+0.004=0.009 WAVES

**Note. **If a scripted account transfers a smart asset, then the fee is increased twice \(the fee increases _**+0.004**_ every time the transaction is validated by account’s script or asset’s script\).

## Trading

Trading on SmartAssets is allowed \(node validates every ExchangeTransaction using scripts of the two assets in AssetPair\).

## Validation

A smart asset’s script validates any of [_**the following transaction**_](/technical-details/transactions-structure.md) types with the asset:

1. ReissueTransaction
2. BurnTransaction
3. TransferTransaction
4. MassTransferTransaction
5. ExchangeTransaction
6. SetAssetScriptTransaction

**Note.** Smart Assets scripts **do not validate orders**. Therefore, although RIDE allows to use `case t : Order => …` branch, in fact this branch does not validate anything when used in SmartAssets’ scripts and will be ignored. So all the logic regarding orders should be moved to `case t : ExchangeTransaction => …` branch. The Sponsorship of smart assets is _**prohibited**_.

## Examples of Scripts for Smart Assets

A smart asset’s script can be changed via [_**SetAssetScriptTransaction**_](/technical-details/data-structures.md) \([fee](/technical-details/transactions-fees.md) on changing is equal to 1 WAVES\).

### _Technical **Notes**_

* The assets that were issued without a script cannot become scripted. You can create an asset that behaves as non-scripted but can be upgraded later, by issuing an asset with a script: **'true' **which means the asset has a script and 'false' when it does not have a script** **\(it's explained with an **example** below\).

* Only the issuer can change the asset's script.

### 1. Create an asset that behaves as non-scripted but can be upgraded later

Here you should use an [IssueTransaction\(Version2\)](/technical-details/transactions-structure.md) and specify the script in this transaction.

Here’s an example of JSON for IssueTxV2, this line ``"script" : "base64:AQa3b8tH"```  contains the compiled script \(“**true**” in the following example\):

```js
{
 "type" : 3,
 "version" : 2,
 "senderPublicKey" : "rWaQhEMTz6saZmZwLR3iuLBhCU2QSq51QmfTX9Je2Mk",
 "name" : "mySmartAsset",
 "description" : "my smart asset",
 "quantity" : 2000000,
 "decimals" : 6,
 "reissuable" : true,
 "fee" : 100000000,
 "timestamp" : 1537456619027,
 "script" : "base64:AQa3b8tH",
 "proofs" : ["3fP2NNKtqRjJQsVXkhXKFcdU7YvRBrJ4Ren6tg8a3g1wuctrfp8PfDap6"]
}
```

### 1. Issue an unburnable asset

```js
match tx {
  case t : BurnTransaction => false
  case _ => true
}
```

### 2. Freeze your assets till the certain height

```js
let targetHeight = 1500000
height >= targetHeight
```

### 3. Require a fee in a certain asset to get a share after each transfer

```js
match tx {
  case t : TransferTransaction =>
    t.feeAssetId == base58'oWgJN6YGZFtZrV8BWQ1PGktZikgg7jzGmtm16Ktyvjd'
  case _ => true
}
```

### 4. Token that can be only transferred with the issuer’s permission \(commitment/debt label\)

```js
match tx {
  case t : TransferTransaction =>
    let issuer = addressFromString("3P6ms9EotRX8JwSrebeTXYVnzpsGCrKWLv4")
    isDefined(getInteger(issuer, toString(t.id)))
  case _ => false
}
```

### 5. Issue an untransferable asset

```js
match tx {
  case t : TransferTransaction | MassTransferTransaction | ExchangeTransaction => false
  case _ => true
}
```

### 6. Asset tradable only with BTC

```js
let BTCId = base58'8LQW8f7P5d5PZM7GtZEBgaqRPGSzS3DfPuiXrURJ4AJS'
match tx {
  case t : ExchangeTransaction =>
    t.sellOrder.assetPair.priceAsset == BTCId || t.sellOrder.assetPair.amountAsset == BTCId
  case _ => true
}
```

### 7. Require using a certain matcher

```js
match tx {
  case t : ExchangeTransaction =>
    t.sender == addressFromString("3PJaDyprvekvPXPuAtxrapacuDJopgJRaU3")
  case _ => true
}
```



