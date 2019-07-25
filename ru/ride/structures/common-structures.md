# Общие структуры

|   #   | Название | Описание |
| :--- | :--- | :--- |
| 1 | [Address](#address) | Структура [адреса](/blockchain/address.md) |
| 2 | [Asset](#asset) | Структура [токена](/blockchain/token.md) |
| 3 | [AssetPair](#asset-pair) | Структура пары токенов ордера |
| 4 | [AttachedPayment](#attached-payment) | Структура платежа [транзакции вызова скрипта](/blockchain/transaction-type/invoke-script-transaction.md) |
| 5 | [BlockInfo](#block-info) | Структура [блока](/blockchain/block.md) |
| 6 | [DataEntry](#data-entry) | Структура записи [хранилища данных аккаунта](/blockchain/account-data-storage.md) |
| 7 | [Invocation](#invocation) | Структура сокращенного представления транзакции вызова скрипта |
| 8 | [Order](#order) | Структура ордера |
| 9 | [ScriptResult](#script-result) | Структура результата выполнения вызываемой функции |
| 10 | [ScriptTransfer](#script-transfer) | Структура перевода токенов |
| 11 | [Transfer](#transfer) | Структура перевода токенов [транзакции массового перевода](/blockchain/transaction-type/mass-transfer-transaction.md) |
| 12 | [TransferSet](#transfer-set) | Структура списка переводов токенов |
| 13 | [WriteSet](#write-set) | Структура списка записей хранилища данных аккаунта |

## Address <a id="address"></a>

Структура [адреса](/blockchain/address.md).

### Конструктор

``` ride
Address(bytes: ByteVector)
```

### Поля

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | bytes | ByteVector | Массив байтов адреса |

## Asset <a id="asset"></a>

Структура [токена](/blockchain/token.md).

### Конструктор

``` ride
Asset(quantity: Int, decimals: Int, issuer: Address, issuerPublicKey: ByteVector, reissuable: Boolean, scripted: Boolean, sponsored: Boolean)
```

### Поля

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | quantity | Int | Количество выпущенных [токенов](/blockchain/token.md) |
| 2 | decimals | Int | Число знаков после запятой у токена |
| 3 | issuer | Address | Адрес аккаунта, который выпустил токен |
| 4 | issuerPublicKey | ByteVector | Публичный ключ аккаунта, выпустившего токен |
| 5 | reissuable | Boolean | true — токен можно довыпускать, false — нельзя довыпускать |
| 6 | scripted | Boolean | true — [смарт-ассет](/blockchain/smart-asset.md), false — обычный токен |
| 7 | sponsored | Boolean | true — токен спонсируемый, false — неспонсируемый |

## AssetPair <a id="asset-pair"></a>

Структура пары токенов ордера.

### Конструктор

``` ride
AssetPair(amountAsset: ByteVector|Unit, priceAsset: ByteVector|Unit)
```

### Поля

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | amountAsset | ByteVector&#124;Unit | Первый токен пары |
| 2 | priceAsset | ByteVector&#124;Unit | Второй токен пары |

## AttachedPayment <a id="attached-payment"></a>

Структура платежа транзакции вызова скрипта.

### Конструктор

``` ride
AttachedPayment(assetId: ByteVector|Unit, amount: Int)
```

### Поля

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | assetId | ByteVector&#124;Unit | ID [токена](/blockchain/token.md) |
| 2 | amount | Int | Сумма платежа |

## BlockInfo <a id="block-info"></a>

Структура [блока](/blockchain/block.md).

### Конструктор

``` ride
BlockInfo(timestamp: Int, height: Int, baseTarget: Int, generationSignature: ByteVector, generator: Address, generatorPublicKey: ByteVector)
```

### Поля

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | timestamp | Int | Unix-время создания [блока](/blockchain/block.md) |
| 2 | height | Int | [Высота блока](/blockchain/block/block-height.md) |
| 3 | baseTarget | Int | Сложность создания блока |
| 4 | generationSignature | ByteVector | Подпись ключевого блока |
| 5 | generator | Address | [Адрес](/blockchain/address.md) аккаунта, который создал блок |
| 6 | generatorPublicKey | ByteVector | Публичный ключ аккаунта, который создал блок |

## DataEntry <a id="data-entry"></a>

Структура записи [хранилища данных аккаунта](/blockchain/account-data-storage.md).

### Конструктор

``` ride
DataEntry(key: String, value: Int|Boolean|ByteVector|String)
```

### Поля

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | key | String | Ключ записи |
| 2 | value | Int&#124;Boolean&#124;ByteVector&#124;String | Значение записи |

## Invocation <a id="invocation"></a>

Структура сокращенного представления транзакции вызова скрипта.

### Конструктор

``` ride
Invocation(caller: Address, callerPublicKey: ByteVector, payment: AttachedPayment|Unit, transactionId: ByteVector, fee: Int, feeAssetId: ByteVector|Unit)
```

### Поля

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | caller | Address | [Адрес](/blockchain/address.md) аккаунта, который отправил транзакцию |
| 2 | callerPublicKey | ByteVector | Публичный ключ аккаунта, который отправил транзакцию |
| 3 | payment | AttachedPayment&#124;Unit | Приложенный платеж |
| 4 | transactionId | ByteVector | ID транзакции |
| 5 | fee | Int | [Комиссия за транзакцию](/blockchain/transaction-fee.md) |
| 6 | feeAssetId | ByteVector&#124;Unit | [Токен](/blockchain/token.md) комиссии за отправку транзакции |

## Order <a id="order"></a>

Структура ордера.

### Конструктор

``` ride
Order(id: ByteVector, matcherPublicKey: ByteVector, assetPair: AssetPair, orderType: Buy|Sell, price: Int, amount: Int, timestamp: Int, expiration: Int, matcherFee: Int, matcherFeeAssetId: ByteVector|Unit, sender: Address, senderPublicKey: ByteVector, bodyBytes: ByteVector, proofs: List[ByteVector])
```

### Поля

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | id | ByteVector | ID ордера |
| 2 | matcherPublicKey | ByteVector | Публичный ключ аккаунта матчера |
| 3 | assetPair | AssetPair | Пара токенов |
| 4 | orderType | Buy&#124;Sell | Тип ордера — продажа или покупка |
| 5 | price | Int | Цена обмениваемого токена |
| 6 | amount | Int | Количество обмениваемых токенов |
| 7 | timestamp | Int | [Unix-время](https://ru.wikipedia.org/wiki/Unix-время) валидации ордера матчером |
| 8 | expiration | Int | Unix-время, когда невыполненный ордер будет отменен |
| 9 | matcherFee | Int | Комиссия за исполнение ордера |
| 10 | matcherFeeAssetId | ByteVector&#124;Unit | Токен [комиссии за транзакцию](/blockchain/transaction-fee.md). В настоящее время возможен только WAVES |
| 11 | sender | Address | [Адрес](/blockchain/address.md) отправителя ордера |
| 12 | senderPublicKey | ByteVector | Публичный ключ аккаунта отправителя ордера |
| 13 | bodyBytes | ByteVector | Массив байтов ордера |
| 14 | proofs | List[ByteVector] | Массив [подтверждений](/blockchain/transaction-proof.md) |

## ScriptResult <a id="script-result"></a>

Структура результата выполнения вызываемой функции.

### Конструктор

``` ride
ScriptResult(writeSet: WriteSet, transferSet: TransferSet)
```

### Поля

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | writeSet | WriteSet | Список записей [хранилища данных аккаунта](/blockchain/account-data-storage.md) |
| 2 | transferSet | TransferSet | Список переводов токенов |

## ScriptTransfer <a id="script-transfer"></a>

Структура перевода токенов.

### Конструктор

``` ride
ScriptTransfer(recipient: Address|Alias, amount: Int, asset: ByteVector|Unit)
```

### Поля

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | recipient | Address&#124;Alias | [Адрес](/blockchain/address.md) или [псевдоним](/blockchain/alias.md) получателя токенов |
| 2 | amount | Int | Количество токенов |
| 3 | asset | ByteVector&#124;Unit | ID токена |

## Transfer <a id="transfer"></a>

Структура перевода [токенов](/blockchain/token.md) транзакции массового перевода.

### Конструктор

``` ride
Transfer(recipient: Address|Alias, amount: Int)
```

### Поля

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | recipient | Address&#124;Alias | Адрес получателя |
| 2 | amount | Int | Количество токенов |

## TransferSet <a id="transfer-set"></a>

Структура списка переводов токенов.

### Конструктор

``` ride
TransferSet(transfers: List[ScriptTransfer])
```

### Поля

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | transfers | List[ScriptTransfer] | Список переводов токенов |

## WriteSet <a id="write-set"></a>

Структура списка записей [хранилища данных аккаунта](/blockchain/account-data-storage.md).

### Конструктор

``` ride
WriteSet(data: List[DataEntry])
```

### Поля

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | data | List[DataEntry] | Список записей хранилища данных аккаунта |
