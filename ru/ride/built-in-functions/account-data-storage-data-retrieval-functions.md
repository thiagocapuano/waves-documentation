# Функции получения данных из хранилища данных аккаунта

|      | Название | Описание | Сложность |
| :--- | :--- | :--- | :--- |
| 1 | [assetBalancе(Address&#124;Alias, ByteVector): Int](#asset-balance)  | Получает баланс токенов на аккаунте по ID токена | 100 |
| 2 | [getBinary(Address&#124;Alias, String): ByteVector&#124;Unit](#get-binary)  | Получает массив байтов по ключу | 100 |
| 3 | [getBinaryValue(Address&#124;Alias, String): ByteVector](#get-binary-value)  | Получает массив байтов по ключу. Выбрасывает исключение если данных нет | 100 |
| 4 | [getBoolean(Address&#124;Alias, String): Boolean&#124;Unit](#get-boolean)  | Получает логическое значение по ключу | 100 |
| 5 | [getBooleanValue(Address&#124;Alias, String): Boolean](#get-boolean-value)  | Получает логическое значение по ключу. Выбрасывает исключение если данных нет | 100 |
| 6 | [getInteger(Address&#124;Alias, String): Int&#124;Unit](#get-integer)  | Получает целочисленные данные по ключу | 100 |
| 7 | [getIntegerValue(Address&#124;Alias, String): Int](#get-integer-value)  | Получает целое число по ключу. Выбрасывает исключение если данных нет | 100 |
| 8 | [getString(Address&#124;Alias, String): String&#124;Unit](#get-string)  | Получает строку по ключу | 100 |
| 9 | [getStringValue(Address&#124;Alias, String): String](#get-string-value)  | Получает строку по ключу. Выбрасывает исключение если данных нет | 100 |
| 10 | [wavesBalance(Address&#124;Alias): Int](#waves-balance)  | Получает баланс аккаунта в [WAVES](/blockchain/token/waves.md) | 100 |

## assetBalance(Address|Alias, ByteVector): Int<a name="asset-balance"></a>

Получает баланс токенов на аккаунте по ID токена.

```
assetBalance(addressOrAlias: Address|Alias, assetId: ByteVector): Int
```

### Параметры

#### addressOrAlias: Address|Alias

[Адрес](/blockchain/address.md) или [псевдоним аккаунта](/blockchain/alias.md).

#### assetId: ByteVector

ID токена.

## getBinary(Address|Alias, String): ByteVector|Unit<a name="get-binary"></a>

Получает массив байтов по ключу.

```
getBinary(addressOrAlias: Address|Alias, key: String): ByteVector|Unit
```

### Параметры

#### addressOrAlias: Address|Alias

[Адрес](/blockchain/address.md) или [псевдоним аккаунта](/blockchain/alias.md).

#### key: String

Ключ.

## getBinaryValue(Address|Alias, String): ByteVector<a name="get-binary-value"></a>

Получает массив байтов по ключу. Выбрасывает исключение если данных нет.

```
getBinaryValue(addressOrAlias: Address|Alias, key: String): ByteVector
```

### Параметры

#### addressOrAlias: Address|Alias

[Адрес](/blockchain/address.md) или [псевдоним аккаунта](/blockchain/alias.md).

#### key: String

Ключ.

## getBoolean(Address|Alias, String): Boolean|Unit<a name="get-boolean"></a>

Получает логическое значение по ключу.

```
getBoolean(addressOrAlias: Address|Alias, key: String): Boolean|Unit
```

### Параметры

#### addressOrAlias: Address|Alias

[Адрес](/blockchain/address.md) или [псевдоним аккаунта](/blockchain/alias.md).

#### key: String

Ключ.

## getBooleanValue(Address|Alias, String): Boolean<a name="get-boolean-value"></a>

Получает логическое значение по ключу. Выбрасывает исключение если данных нет.

```
getBooleanValue(addressOrAlias: Address|Alias, key: String): Boolean
```

### Параметры

#### addressOrAlias: Address|Alias

[Адрес](/blockchain/address.md) или [псевдоним аккаунта](/blockchain/alias.md).

#### key: String

Ключ.

## getInteger(Address|Alias, String): Int|Unit<a name="get-integer"></a>

Получает целое число по ключу.

```
getInteger(addressOrAlias: Address|Alias, key: String): Int|Unit
```

### Параметры

#### addressOrAlias: Address|Alias

[Адрес](/blockchain/address.md) или [псевдоним аккаунта](/blockchain/alias.md).

#### key: String

Ключ.

## getIntegerValue(Address|Alias, String): Int<a name="get-integer-value"></a>

Получает целое число по ключу. Выбрасывает исключение если данных нет.

```
getIntegerValue(addressOrAlias: Address|Alias, key: String): Int
```

### Параметры

#### addressOrAlias: Address|Alias

[Адрес](/blockchain/address.md) или [псевдоним аккаунта](/blockchain/alias.md).

#### key: String

Ключ.

## getString(Address|Alias, String): String|Unit<a name="get-string"></a>

Получает строку по ключу.

```
getString(addressOrAlias: Address|Alias, key: String): String|Unit
```

### Параметры

#### addressOrAlias: Address|Alias

[Адрес](/blockchain/address.md) или [псевдоним аккаунта](/blockchain/alias.md).

#### key: String

Ключ.

## getStringValue(Address|Alias, String): String<a name="get-string-value"></a>

Получает строку по ключу. Выбрасывает исключение если данных нет.

```
getStringValue(addressOrAlias: Address|Alias, key: String): String
```

### Параметры

#### addressOrAlias: Address|Alias

[Адрес](/blockchain/address.md) или [псевдоним аккаунта](/blockchain/alias.md).

#### key: String

Ключ.

## wavesBalance(Address|Alias): Int<a name="waves-balance"></a>

Получает баланс аккаунта в [WAVES](/blockchain/token/waves.md).

```
wavesBalance(addressOrAlias: Address|Alias): Int
```

### Параметры

#### addressOrAlias: Address|Alias

[Адрес](/blockchain/address.md) или [псевдоним аккаунта](/blockchain/alias.md).
