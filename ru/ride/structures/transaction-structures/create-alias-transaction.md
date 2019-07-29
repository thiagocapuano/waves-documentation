# CreateAliasTransaction

Структура [транзакции создания псевдонима](/blockchain/transaction-type/alias-transaction.md).

## Конструктор

``` ride
CreateAliasTransaction(alias: String, id: ByteVector, fee: Int, timestamp: Int, version: Int, sender: Address, senderPublicKey: ByteVector, bodyBytes: ByteVector, proofs: List[ByteVector])
```

## Поля структуры

| # | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | alias | String | [Псевдоним](/blockchain/alias.md) |
| 2 | id | ByteVector | [ID транзакции](/blockchain/transaction.md#transaction-id) |
| 3 | fee | Int | [Комиссия за транзакцию](/blockchain/transaction-fee.md) |
| 4 | timestamp | Int | [Unix-время](https://ru.wikipedia.org/wiki/Unix-время) отправки транзакции в блокчейн |
| 5 | version | Int | Версия [транзакции создания псевдонима](/blockchain/transaction-type/alias-transaction.md) |
| 6 | sender | Address | [Адрес](/blockchain/address.md) отправителя транзакции |
| 7 | senderPublicKey | ByteVector | Публичный ключ отправителя транзакции |
| 8 | bodyBytes | ByteVector | [Байты тела транзакции](/blockchain/transaction-body-bytes.md) |
| 9 | proofs | List[ByteVector] | Список [подтверждений](/blockchain/transaction-proof.md) |
