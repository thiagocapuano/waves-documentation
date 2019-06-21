# Функции получения данных из блокчейна

|      | Название | Описание | Сложность |
| :--- | :--- | :--- | :--- |
|   1  | [assetInfo(ByteVector): Аsset&#124;Unit](#asset-info) | Получает информацию о токене | 100 |
|   2  | [blockInfoByHeight(Int): BlockInfo&#124;Unit](#block-info-by-height) | Получает информацию о [блоке](/blockchain/block.md) по его [высоте](/blockchain/block-height.md) | 100 |
|   3  | [transactionHeightById(ByteVector): Int&#124;Unit](#transaction-height-by-id) | Получает [высоту блока](/blockchain/block-height.md) транзакции | 100 |
|   4  | [transferTransactionById(ByteVector): TransferTransaction&#124;Unit](#transfer-transaction-by-id) | Получает данные транзакции перевода | 100 |

## <a id="asset-info"></a>assetInfo

Получает информацию о токене.

```
assetInfo(id: ByteVector): Аsset|Unit
```

### Параметры

#### `id`: ByteVector

ID токена.

## <a id="block-info-by-height"></a>blockInfoByHeight

Получает информацию о [блоке](/blockchain/block.md) по его [высоте](/blockchain/block-height.md).

```
blockInfoByHeight(height: Int): BlockInfo|Unit
```

### Параметры

#### `height`: Int

Высота блока.

## <a id="transaction-height-by-id"></a>transactionHeightById

Получает [высоту блока](/blockchain/block-height.md) транзакции.

```
transactionHeightById(id: ByteVector): Int|Unit
```

### Параметры

#### `id`: ByteVector

ID транзакции.

## <a id="transfer-transaction-by-id"></a>transferTransactionById

Получает данные транзакции перевода.

```
transferTransactionById(id: ByteVector): TransferTransaction|Unit
```

### Параметры

#### `id`: ByteVector

ID транзакции перевода.
