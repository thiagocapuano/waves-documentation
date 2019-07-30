# Common structures

|   #   | Name | Description |
| :--- | :--- | :--- |
| 1 | [Address](#address) | The structure of an [address](/blockchain/address.md) |
| 2 | [Asset](#asset) | The structure of a [token](/blockchain/token.md) |
| 3 | [AssetPair](#asset-pair) | The structure of a pair of tokens of an order |
| 4 | [AttachedPayment](#attached-payment) | The structure of an invoke script transaction payment |
| 5 | [BlockInfo](#block-info) | The structure of a [block](/blockchain/block.md) |
| 6 | [DataEntry](#data-entry) | The structure of a data record of an [account data storage](/blockchain/account-data-storage.md) |
| 7 | [Invocation](#invocation) | The structure of the abbreviated representation of an invoke script transaction |
| 8 | [Order](#order) | The structure of an order |
| 9 | [ScriptResult](#script-result) | The structure of the execution result of a callable function |
| 10 | [ScriptTransfer](#script-transfer) | The structure of a token transfer |
| 11 | [Transfer](#transfer) | The structure of a mass transfer transaction token transfer |
| 12 | [TransferSet](#transfer-set) | The structure of a list of token transfers |
| 13 | [WriteSet](#write-set) | The structure of a list of data records of an account data storage |

## Address <a id="address"></a>

The structure of an [address](/blockchain/address.md).

### Constructor

``` ride
Address(bytes: ByteVector)
```

### Fields

|   #   | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | bytes | ByteVector | The array of bytes of an address |

## Asset <a id="asset"></a>

The structure of a [token](/blockchain/token.md).

### Constructor

``` ride
Asset(id: ByteVector, quantity: Int, decimals: Int, issuer: Address, issuerPublicKey: ByteVector, reissuable: Boolean, scripted: Boolean, sponsored: Boolean)
```

### Fields

|   #   | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | id | ByteVector | The ID of a token |
| 2 | quantity | Int | The number of issued tokens |
| 3 | decimals | Int | The number of decimal places |
| 4 | issuer | Address | The [address](/blockchain/address.md) of the [account](/blockchain/account.md) that issued a token |
| 5 | issuerPublicKey | ByteVector | The public key of the account that issued a token |
| 6 | reissuable | Boolean | true — token can be reissued, false — cannot be reissued |
| 7 | scripted | Boolean | true — smart asset, false — regular token |
| 8 | sponsored | Boolean | true — token can be sponsored, false — cannot be sponsored |

## AssetPair <a id="asset-pair"></a>

The structure of a pair of [tokens](/blockchain/token.md) of an order.

### Constructor

``` ride
AssetPair(amountAsset: ByteVector|Unit, priceAsset: ByteVector|Unit)
```

### Fields

|   #   | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | amountAsset | ByteVector&#124;Unit | The first token of a pair |
| 2 | priceAsset | ByteVector&#124;Unit | The second token of a pair |

## AttachedPayment <a id="attached-payment"></a>

The structure of an [invoke script transaction](/blockchain/transaction-type/invoke-script-transaction.md) payment.

### Constructor

``` ride
AttachedPayment(assetId: ByteVector|Unit, amount: Int)
```

### Fields

|   #   | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | assetId | ByteVector&#124;Unit | The ID of a [token](/blockchain/token.md) |
| 2 | amount | Int | The payment amount |

## BlockInfo <a id="block-info"></a>

The structure of a [block](/blockchain/block.md).

### Constructor

``` ride
BlockInfo(timestamp: Int, height: Int, baseTarget: Int, generationSignature: ByteVector, generator: Address, generatorPublicKey: ByteVector)
```

### Fields

|   #   | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | timestamp | Int | The [Unix time](https://en.wikipedia.org/wiki/Unix-time) of the creation of a block |
| 2 | height | Int | The [block height](/blockchain/block/block-height.md) |
| 3 | baseTarget | Int | The complexity of the block creation |
| 4 | generationSignature | ByteVector | The signature of a key block |
| 5 | generator | Address | The [address](/blockchain/address.md) of an [/blockchain/account.md) account that created a block |
| 6 | generatorPublicKey | ByteVector | The public key of the account that created a block |

## DataEntry <a id="data-entry"></a>

The structure of a data record of an [account data storage](/blockchain/account-data-storage.md).

### Constructor

``` ride
DataEntry(key: String, value: Int|Boolean|ByteVector|String)
```

### Fields

|   #   | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | key | String | The key of a record |
| 2 | value|Int&#124;Boolean&#124;ByteVector&#124;String | The value of a record |

## Invocation <a id="invocation"></a>

The structure of the abbreviated representation of an invoke script transaction.

### Constructor

``` ride
Invocation(caller: Address, callerPublicKey: ByteVector, payment: AttachedPayment|Unit, transactionId: ByteVector, fee: Int, feeAssetId: ByteVector|Unit)
```

### Fields

|   #   | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | caller | Address | The address of an [account](/blockchain/account.md) that sent a transaction |
| 2 | callerPublicKey | ByteVector | The public key of an account that sent a transaction |
| 3 | payment | AttachedPayment&#124;Unit | The attached payment |
| 4 | transactionId | ByteVector | The ID of a transaction |
| 5 | fee | Int | The transaction fee |
| 6 | feeAssetId | ByteVector&#124;Unit | The [token](/blockchain/token.md) of a transaction fee |

## Order <a id="order"></a>

The structure of an order.

### Constructor

``` ride
Order(id: ByteVector, matcherPublicKey: ByteVector, assetPair: AssetPair, orderType: Buy|Sell, price: Int, amount: Int, timestamp: Int, expiration: Int, matcherFee: Int, matcherFeeAssetId: ByteVector|Unit, sender: Address, senderPublicKey: ByteVector, bodyBytes: ByteVector, proofs: List[ByteVector])
```

### Fields

|   #   | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | id | ByteVector | The ID of an order |
| 2 | matcherPublicKey | ByteVector | The public key of a matcher |
| 3 | assetPair | AssetPair | The pair of [tokens](/blockchain/token.md) |
| 4 | orderType | Buy&#124;Sell | The type of an order — selling or buying |
| 5 | price | Int | The price of a token to exchange |
| 6 | amount | Int | The number of tokens to exchange |
| 7 | timestamp | Int | The [Unix time](https://en.wikipedia.org/wiki/Unix-time) of the validation of an order by a matcher  |
| 8 | expiration | Int | The Unix time when an uncompleted order will be cancelled |
| 9 | matcherFee | Int | The [transaction fee](/blockchain/transaction-fee.md) |
| 10 | matcherFeeAssetId | ByteVector&#124;Unit | The token of a transaction fee. Currently, can only be [WAVES](/blockchain/token/waves.md) |
| 11 | sender | Address | The [address](/blockchain/address.md) of the sender of an order |
| 12 | senderPublicKey | ByteVector | The public key of the sender of an order |
| 13 | bodyBytes | ByteVector | The array of bytes of an order |
| 14 | proofs | List[ByteVector] | The array of [proofs](/blockchain/transaction-proof.md) |

## ScriptResult <a id="script-result"></a>

The structure of the execution result of a callable function.

### Constructor

``` ride
ScriptResult(writeSet: WriteSet, transferSet: TransferSet)
```

### Fields

|   #   | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | writeSet | WriteSet | The list of records of an [account data storage](/blockchain/transaction-proof.md) |
| 2 | transferSet | TransferSet | The list of [tokens](/blockchain/token.md) of a transfer |

## ScriptTransfer <a id="script-transfer"></a>

The structure of a [token](/blockchain/token.md) transfer.

### Constructor

``` ride
ScriptTransfer(recipient: Address|Alias, amount: Int, asset: ByteVector|Unit)
```

### Fields

|   #   | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | recipient | Address&#124;Alias | The [address](/blockchain/address.md) or the [alias](/blockchain/alias.md) of a recipient of tokens |
| 2 | amount | Int | The number of tokens |
| 3 | asset | ByteVector&#124;Unit | The ID of a token |

## Transfer <a id="transfer"></a>

The structure of a [mass transfer transaction](/blockchain/transaction-type/mass-transfer-transaction.md) [token](/blockchain/token.md) transfer.

### Constructor

``` ride
Transfer(recipient: Address|Alias, amount: Int)
```

### Fields

|   #   | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | recipient | Address&#124;Alias | The address of a recipient of tokens |
| 2 | amount | Int | Number of tokens |

## TransferSet <a id="transfer-set"></a>

The structure of a list of [token](/blockchain/token.md) transfers.

### Constructor

``` ride
TransferSet(transfers: List[ScriptTransfer])
```

### Fields

|   #   | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | transfers | List[ScriptTransfer] | The list of token transfers |

## WriteSet <a id="write-set"></a>

The structure of a list of data records of an [account data storage](/blockchain/account-data-storage.md).

### Constructor

``` ride
WriteSet(data: List[DataEntry])
```

### Fields

|   #   | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | data | List[DataEntry] | The list of data records of an account data storage |
