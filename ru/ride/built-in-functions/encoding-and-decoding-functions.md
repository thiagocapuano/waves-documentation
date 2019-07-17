# Функции кодирования и декодирования

## Функции кодирования

| # | Название | Описание | Сложность |
| :--- | :--- | :--- | :--- |
| 1 | [blake2b256(ByteVector): ByteVector](#blake2b256) | Хеширует массив байтов с помощью алгоритма [blake2b256](https://ru.wikipedia.org/wiki/BLAKE_%28хеш-функция%29) | 10 |
| 2 | [keccak256(ByteVector): ByteVector](#keccak256) | Хеширует массив байтов с помощью алгоритма [SHA-3-256](https://ru.wikipedia.org/wiki/SHA-3) | 10 |
| 3 | [sha256(ByteVector): ByteVector](#sha256) | Хеширует массив байтов с помощью алгоритма [SHA-256](https://ru.wikipedia.org/wiki/SHA-2) | 10 |
| 4 | [toBase16String(ByteVector): String](#to-base-16-string) | Кодирует массив байтов в строку [Base16](https://ru.wikipedia.org/wiki/Шестнадцатеричная_система_счисления) | 10 |
| 5 | [toBase58String(ByteVector): String](#to-base-58-string) | Кодирует массив байтов в строку [Base58](https://ru.wikipedia.org/wiki/Base58) | 10 |
| 6 | [toBase64String(ByteVector): String](#to-base-64-string) | Кодирует массив байтов в строку [Base64](https://ru.wikipedia.org/wiki/Base64) | 10 |

## Функции декодирования

| # | Название | Описание | Сложность |
| :--- | :--- | :--- | :--- |
| 1 | [addressFromString(String): Address&#124;Unit](#address-from-string)| Декодирует адрес из строки [Base58](https://ru.wikipedia.org/wiki/Base58) | 124 |
| 2 | [addressFromStringValue(String): Address](#address-from-string-value) | Декодирует адрес из строки [Base58](https://ru.wikipedia.org/wiki/Base58).<br>Выбрасывает исключение, если адрес невозможно декодировать | 124 |
| 3 | [fromBase16String(String): ByteVector](#from-base-16-string) | Декодирует строку [Base16](https://ru.wikipedia.org/wiki/Шестнадцатеричная_система_счисления) в массив байтов | 10 |
| 4 | [fromBase58String(String): ByteVector](#from-base-58-string) | Декодирует строку [Base58](https://ru.wikipedia.org/wiki/Base58) в массив байтов | 10 |
| 5 | [fromBase64String(String): ByteVector](#from-base-64-string)| Декодирует строку [Base64](https://ru.wikipedia.org/wiki/Base64) в массив байтов | 10 |

## blake2b256(ByteVector): ByteVector<a id="blake2b256"></a>

Хеширует массив байтов с помощью алгоритма [blake2b256](https://ru.wikipedia.org/wiki/BLAKE_(хеш-функция))

``` ride
blake2b256(bytes: ByteVector): ByteVector
```

### Параметры

#### `bytes`: ByteVector

Массив байтов для хеширования.

## keccak256(ByteVector): ByteVector<a id="keccak256"></a>

Хеширует массив байтов с помощью алгоритма [SHA-3-256](https://ru.wikipedia.org/wiki/SHA-3).

``` ride
keccak256(bytes: ByteVector): ByteVector
```

### Параметры

#### `bytes`: ByteVector

Массив байтов для хеширования.

## sha256(ByteVector): ByteVector<a id="sha256"></a>

Хеширует массив байтов с помощью алгоритма [SHA-256](https://ru.wikipedia.org/wiki/SHA-2).

``` ride
sha256(bytes: ByteVector): ByteVector
```

### Параметры

#### `bytes`: ByteVector

Массив байтов для хеширования.

## toBase16String(ByteVector): String<a id="to-base-16-string"></a>

Кодирует массив байтов в строку [Base16](https://ru.wikipedia.org/wiki/Шестнадцатеричная_система_счисления).

``` ride
toBase16String(bytes: ByteVector): String
```

### Параметры

#### `bytes`: ByteVector

Массив байтов для кодирования.

## toBase58String(ByteVector): String<a id="to-base-58-string"></a>

Кодирует массив байтов в строку [Base58](https://ru.wikipedia.org/wiki/Base58).

``` ride
toBase58String(bytes: ByteVector): String
```

### Параметры

#### `bytes`: ByteVector

Массив байтов для кодирования.

## toBase64String(ByteVector): String<a id="to-base-64-string"></a>

Кодирует массив байтов в строку [Base64](https://ru.wikipedia.org/wiki/Base64).

``` ride
toBase64String(bytes: ByteVector): String
```

### Параметры

#### `bytes`: ByteVector

Массив байтов для кодирования.

### addressFromString(String): Address|Unit<a id="address-from-string"></a>

Декодирует адрес из строки [Base58](https://ru.wikipedia.org/wiki/Base58).

``` ride
addressFromString(string: String): Address|Unit
```

### Параметры

#### `string`: String

Строка для декодирования.

## addressFromStringValue(String): Address <a id="address-from-string-value"></a>

Декодирует адрес из строки [Base58](https://ru.wikipedia.org/wiki/Base58).

Выбрасывает исключение, если адрес невозможно декодировать.

``` ride
addressFromStringValue(string: String): Address
```

### Параметры

#### `string`: String

Строка для декодирования.

## fromBase16String(String): ByteVector<a id="from-base-16-string"></a>

Декодирует строку [Base16](https://ru.wikipedia.org/wiki/Шестнадцатеричная_система_счисления) в массив байтов.

``` ride
fromBase16String(str: String): ByteVector
```

### Параметры

#### `str`: String

Строка для декодирования.

## fromBase58String(String): ByteVector<a id="from-base-58-string"></a>

Декодирует строку [Base58](https://ru.wikipedia.org/wiki/Base58) в массив байтов.

``` ride
fromBase58String(str: String): ByteVector
```

### Параметры

#### `str`: String

Строка для декодирования.

## fromBase64String(String): ByteVector<a id="from-base-64-string"></a>

Декодирует строку [Base64](https://ru.wikipedia.org/wiki/Base64) в массив байтов.

``` ride
fromBase64String(str: String): ByteVector
```

### Параметры

#### `str`: String

Строка для декодирования.
