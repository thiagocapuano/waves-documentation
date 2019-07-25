# BurnTransaction

Структура [транзакции сжигания токена](/blockchain/transaction-type/burn-transaction.md).

## Конструктор

``` ride
BurnTransaction(quantity: Int, assetId: ByteVector, id: ByteVector, fee: Int, timestamp: Int, version: Int, sender: Address, senderPublicKey: ByteVector, bodyBytes: ByteVector, proofs: List[ByteVector])
```

## Поля

| # | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | quantity | Int | Количество сжигаемого [токена](/blockchain/token.md) |
| 2 | assetId | ByteVector | ID сжигаемого токена |
| 3 | id | ByteVector | [ID транзакции](/blockchain/transaction#transaction-id) |
| 4 | fee | Int | [Комиссия за транзакцию](/blockchain/transaction-fee.md) |
| 5 | timestamp | Int | [Unix-время](https://ru.wikipedia.org/wiki/Unix-время) отправки транзакции в [блокчейн](/blockchain/blockchain.md) |
| 6 | version | Int | Версия [бинарного формата](https://docs.wavesplatform.com/en/blockchain/binary-format/transaction-binary-format/burn-transaction-binary-format.html) транзакции сжигания токена |
| 7 | sender | Address | [Адрес](/blockchain/address.md) отправителя транзакции |
| 8 | senderPublicKey | ByteVector | Публичный ключ отправителя транзакции |
| 9 | bodyBytes | ByteVector | [Байты тела транзакции](/blockchain/transaction-body-bytes.md) |
| 10 | proofs | List[ByteVector] | Список [подтверждений](/blockchain/transaction-proof.md) |
