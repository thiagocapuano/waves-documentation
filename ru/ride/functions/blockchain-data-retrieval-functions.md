# Функции получения данных из блокчейна

|      | Название | Описание | Сложность |
| :--- | :--- | :--- | :--- |
|   1  | <a href="#assetInfo">assetInfo(ByteVector): Аsset|Unit</a> | Получает информацию о токене | 100 |
|   2  | <a href="#blockInfoByHeight">blockInfoByHeight(Int): BlockInfo|Unit</a> | Получает информацию о [блоке]() по его [высоте]() | 100 |
|   3  | <a href="#transactionHeightById">transactionHeightById(ByteVector): Int|Unit</a> | Получает [высоту блока]() транзакции | 100 |
|   4  | <a href="#transferTransactionById">transferTransactionById(ByteVector): TransferTransaction|Unit</a> | Получает данные транзакции перевода | 100 |

## assetInfo

Получает информацию о токене.

```
assetInfo(id: ByteVector): Аsset|Unit
```

### Параметры

#### `id`: ByteVector

ID токена.

## blockInfoByHeight

Получает информацию о [блоке]() по его [высоте]().

```
blockInfoByHeight(height: Int): BlockInfo|Unit
```

### Параметры

#### `height`: Int

Высота блока.

## transactionHeightById

Получает [высоту блока]() транзакции.

```
transactionHeightById(id: ByteVector): Int|Unit
```

### Параметры

#### `id`: ByteVector

ID транзакции.

## transferTransactionById

Получает данные транзакции перевода.

```
transferTransactionById(id: ByteVector): TransferTransaction|Unit
```

### Параметры

#### `id`: ByteVector

ID транзакции перевода.
