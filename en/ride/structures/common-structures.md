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

Структура [адреса](/blockchain/address.md).

### Конструктор

``` ride
Address(bytes: ByteVector)
```

### Поля структуры

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | bytes | ByteVector | The array of bytes of an address |

## Asset <a id="asset"></a>

Структура [токена](/blockchain/token.md).

### Конструктор

``` ride
Asset(id: ByteVector, quantity: Int, decimals: Int, issuer: Address, issuerPublicKey: ByteVector, reissuable: Boolean, scripted: Boolean, sponsored: Boolean)
```

### Поля структуры

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | id | ByteVector | The ID of a token |
| 2 | quantity | Int | The number of issued tokens |
| 3 | decimals | Int | The number of decimal places |
| 4 | issuer | Address | The address of the account that issued a token |
| 5 | issuerPublicKey | ByteVector | The public key of the account that issued a token |
| 6 | reissuable | Boolean | true — token can be reissued, false — cannot be reissued |
| 7 | scripted | Boolean | true — smart asset, false — regular token |
| 8 | sponsored | Boolean | true — token can be sponsored, false — cannot be sponsored |

## AssetPair <a id="asset-pair"></a>

Структура пары токенов ордера.

### Конструктор

``` ride
AssetPair(amountAsset: ByteVector|Unit, priceAsset: ByteVector|Unit)
```

### Поля структуры

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | amountAsset | ByteVector|Unit | The first token of a pair |
| 2 | priceAsset | ByteVector|Unit | The second token of a pair |

## AttachedPayment <a id="attached-payment"></a>

Структура платежа транзакции вызова скрипта.

### Конструктор

``` ride
AttachedPayment(assetId: ByteVector|Unit, amount: Int)
```

### Поля структуры

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | assetId | ByteVector|Unit | The ID of a token |
| 2 | amount | Int | The payment amount |

## BlockInfo <a id="block-info"></a>

Структура [блока](/blockchain/block.md).

### Конструктор

``` ride
BlockInfo(timestamp: Int, height: Int, baseTarget: Int, generationSignature: ByteVector, generator: Address, generatorPublicKey: ByteVector)
```

### Поля структуры

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | timestamp | Int | The Unix time of the creation of a block |
| 2 | height | Int | The block height |
| 3 | baseTarget | Int | The complexity of the block creation |
| 4 | generationSignature | ByteVector | The signature of a key block |
| 5 | generator | Address | The address of an account that created a block |
| 6 | generatorPublicKey | ByteVector | The public key of the account that created a block |

## DataEntry <a id="data-entry"></a>

Структура записи [хранилища данных аккаунта](/blockchain/account-data-storage.md).

### Конструктор

``` ride
DataEntry(key: String, value: Int|Boolean|ByteVector|String)
```

### Поля структуры

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | key | String | The key of a record |
| 2 | value | Int|Boolean|ByteVector|String | The value of a record |

## Invocation <a id="invocation"></a>

Структура сокращенного представления транзакции вызова скрипта.

### Конструктор

``` ride
Invocation(caller: Address, callerPublicKey: ByteVector, payment: AttachedPayment|Unit, transactionId: ByteVector, fee: Int, feeAssetId: ByteVector|Unit)
```

### Поля структуры

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | caller | Address | The address of an account that sent a transaction |
| 2 | callerPublicKey | ByteVector | The public key of an account that sent a transaction |
| 3 | payment | AttachedPayment|Unit | The attached payment |
| 4 | transactionId | ByteVector | The ID of a transaction |
| 5 | fee | Int | The transaction fee |
| 6 | feeAssetId | ByteVector|Unit | The token of a transaction fee |

## Order <a id="order"></a>

Структура ордера.

### Конструктор

``` ride
Order(id: ByteVector, matcherPublicKey: ByteVector, assetPair: AssetPair, orderType: Buy|Sell, price: Int, amount: Int, timestamp: Int, expiration: Int, matcherFee: Int, matcherFeeAssetId: ByteVector|Unit, sender: Address, senderPublicKey: ByteVector, bodyBytes: ByteVector, proofs: List[ByteVector])
```

### Поля структуры

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | id | ByteVector | The ID of an order |
| 2 | matcherPublicKey | ByteVector | The public key of a matcher |
| 3 | assetPair | AssetPair | The pair of tokens |
| 4 | orderType | Buy|Sell | The type of an order — selling or buying |
| 5 | price | Int | The price of a token to exchange |
| 6 | amount | Int | The number of tokens to exchange |
| 7 | timestamp | Int | The Unix time of the validation of an order by a matcher  |
| 8 | expiration | Int | The Unix time when an uncompleted order will be cancelled |
| 9 | matcherFee | Int | The transaction fee. |
| 10 | matcherFeeAssetId | ByteVector|Unit | The token of a transaction fee. Currently, can only be WAVES |
| 11 | sender | Address | The address of the sender of an order |
| 12 | senderPublicKey | ByteVector | The public key of the sender of an order |
| 13 | bodyBytes | ByteVector | The array of bytes of an order |
| 14 | proofs | List[ByteVector] | The array of proofs |

## ScriptResult <a id="script-result"></a>

Структура результата выполнения вызываемой функции.

### Конструктор

``` ride
ScriptResult(writeSet: WriteSet, transferSet: TransferSet)
```

### Поля структуры

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | writeSet | WriteSet | The list of records of an account data storage |
| 2 | transferSet | TransferSet | The list of tokens of a transfer |

## ScriptTransfer <a id="script-transfer"></a>

Структура перевода токенов.

### Конструктор

``` ride
ScriptTransfer(recipient: Address|Alias, amount: Int, asset: ByteVector|Unit)
```

### Поля структуры

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | recipient | Address|Alias | The address or the alias of a recipient of tokens |
| 2 | amount | Int | The number of tokens |
| 3 | asset | ByteVector|Unit | The ID of a token |

## Transfer <a id="transfer"></a>

Структура перевода токенов транзакции массового перевода.

### Конструктор

``` ride
Transfer(recipient: Address|Alias, amount: Int)
```

### Поля структуры

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | recipient | Address|Alias | The address of a recipient of tokens |
| 2 | amount | Int | Number of tokens |

## TransferSet <a id="transfer-set"></a>

Структура списка переводов токенов.

### Конструктор

``` ride
TransferSet(transfers: List[ScriptTransfer])
```

### Поля структуры

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | transfers | List[ScriptTransfer] | The list of token transfers |

## WriteSet <a id="write-set"></a>

Структура списка записей хранилища данных аккаунта.

### Конструктор

``` ride
WriteSet(data: List[DataEntry])
```

### Поля структуры

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | data | List[DataEntry] | The list of data records of an account data storage. |
