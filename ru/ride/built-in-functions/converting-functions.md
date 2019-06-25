# Функции конвертации

|   #   | Название | Описание | Сложность |
| :--- | :--- | :--- | :--- |
| 1 | [addressFromPublicKey(ByteVector): Address](#address-from-public-key)  | Конвертирует публичный ключ аккаунта в [адрес](/blockchain/address.md) | 82 |
| 2 | [parseInt(String): Int&#124;Unit](#parse-int)  | Конвертирует строку в целое число | 20 |
| 3 | [parseIntValue(String): Int](#parse-int-value)  | Конвертирует строку в целое число.<br>Выбрасывает исключение, если строка не может быть сконвертирована | 20 |
| 4 | [toBytes(Boolean): ByteVector](#to-bytes-boolean)  | Конвертирует логическое значение в массив байтов | 1 |
| 5 | [toBytes(Int): ByteVector](#to-bytes-int)  | Конвертирует целое число в массив байтов | 1 |
| 6 | [toBytes(String): ByteVector](#to-bytes-string)  | Конвертирует строку в массив байтов | 1 |
| 7 | [toInt(ByteVector): Int](#to-int)  | Конвертирует массив байтов в целое число | 10 |
| 8 | [toInt(ByteVector, Int): Int](#to-int-index)  | Конвертирует массив байтов начиная с определенного индекса в целое число | 10 |
| 9 | [toString(Boolean): String](#to-string-boolean)  | Конвертирует логическое значение в строку | 1 |
| 10 | [toString(Int): String](#to-string-int)  | Конвертирует целое число в строку | 1 |
| 11 | [toUtf8String(ByteVector): String](#to-utf8-string)  | Конвертирует массив байтов в строку в UTF-8 | 20 |

## addressFromPublicKey(ByteVector): Address<a id="#address-from-public-key"></a>

Конвертирует публичный ключ аккаунта в адрес.

``` ride
addressFromPublicKey(publicKey: ByteVector): Int
```

### Параметры

`publicKey`: ByteVector

Публичный ключ аккаунта.

## parseInt(String): Int&#124;Unit<a id="#parse-int"></a>

Конвертирует строку в целое число.

``` ride
parseInt(str: String): Int|Unit
```

### Параметры

`str`: String

Строка для конвертации.

## parseIntValue(String): Int<a id="#parse-int-value"></a>

Конвертирует строку в целое число.

Выбрасывает исключение, если строка не может быть сконвертирована.

``` ride
parseIntValue(str: String): Int
```

### Параметры

`str`: String

Строка для конвертации.

## toBytes(Boolean): ByteVector<a id="#to-bytes-boolean"></a>

Конвертирует логическое значение в массив байтов.

``` ride
toBytes(b: Boolean): ByteVector
```

### Параметры

`b`: Boolean

Логическое значение для конвертации.

## toBytes(Int): ByteVector<a id="#to-bytes-int"></a>

Конвертирует целое число в массив байтов.

``` ride
toBytes(n: Int): ByteVector
```

### Параметры

`n`: Int

Целое число для конвертации.

## toBytes(String): ByteVector<a id="#to-bytes-string"></a>

Конвертирует строку в массив байтов.

``` ride
toBytes(s: String): ByteVector
```

### Параметры

`s`: String

Строка для конвертации.

## toInt(ByteVector): Int<a id="#to-int"></a>

Конвертирует массив байтов в целое число.

``` ride
toInt(bin: ByteVector): Int
```

### Параметры

`bin`: ByteVector

Массив байтов для конвертации.

## toInt(ByteVector, Int): Int<a id="#to-int-index"></a>

Конвертирует массив байтов начиная с определенного индекса в целое число.

``` ride
toInt(bin: ByteVector, offset: Int): Int
```

### Параметры

`bin`: ByteVector

Массив байтов для конвертации.

`offset`: Int

Индекс.

## toString(Boolean): String<a id="#to-string-boolean"></a>

Конвертирует логическое значение в строку.

``` ride
toString(b: Boolean): String
```

### Параметры

`b`: Boolean

Логическое значение для конвертации.

## toString(Int): String<a id="#to-string-int"></a>

Конвертирует целое число в строку.

``` ride
toString(n: Int): String
```

### Параметры

`n`: Int

Целое число для конвертации.

## toUtf8String(ByteVector): String<a id="#to-utf8-string"></a>

Конвертирует массив байтов в строку в UTF-8.

``` ride
toUtf8String(u: ByteVector): String
```

### Параметры

`u`: ByteVector

Массив байтов для конвертации.
