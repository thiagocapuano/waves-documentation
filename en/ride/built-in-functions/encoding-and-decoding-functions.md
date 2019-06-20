# Encoding and decoding functions

## Encoding functions

| Name | Description | Complexity |
| :--- | :--- | :--- |
| <a href= "#blake2b256">blake2b256(ByteVector): ByteVector</a> | [BLAKE-256](https://en.wikipedia.org/wiki/BLAKE_%28hash_function%29) hash function | 10 |
| <a href= "#keccak256">keccak256(ByteVector): ByteVector</a> | [SHA-3-256](https://en.wikipedia.org/wiki/SHA-3) hash function | 10 |
| <a href= "#sha256">sha256(ByteVector): ByteVector</a> | [SHA-256](https://en.wikipedia.org/wiki/SHA-2) hash function | 10 |
| <a href= "#toBase16String">toBase16String(ByteVector): String</a> | Encodes array of bytes to [Base16](https://en.wikipedia.org/wiki/Hexadecimal) string | 10 |
| <a href= "#toBase58String">toBase58String(ByteVector): String</a> | Encodes array of bytes to [Base58](https://en.wikipedia.org/wiki/Base58) string | 10 |
| <a href= "#toBase64String">toBase64String(ByteVector): String</a> | Encodes array of bytes to [Base64](https://en.wikipedia.org/wiki/Base64) string | 10 |


## Decoding functions

| Name | Description | Complexity |
| :--- | :--- | :--- |
| <a href= "#addressFromString">addressFromString(String): Address|Unit</a> | Decodes address from [Base58](https://en.wikipedia.org/wiki/Base58) string | 124 |
| <a href= "#addressFromStringValue">addressFromStringValue(String): Address</a> | Decodes address from [Base58](https://en.wikipedia.org/wiki/Base58) string.<br>Raises an exception if the string can not be parsed | 124 |
| <a href= "#fromBase16String">fromBase16String(String): ByteVector</a> | Decodes [Base16](https://en.wikipedia.org/wiki/Hexadecimal) string to an array of bytes | 10 |
| <a href= "#fromBase58String">fromBase58String(String): ByteVector</a> | Decodes [Base58](https://en.wikipedia.org/wiki/Base58) string to an array of bytes | 10 |
| <a href= "#fromBase64String">fromBase64String(String): ByteVector</a>| Decodes [Base64](https://en.wikipedia.org/wiki/Base64) string to an array of bytes | 10 |



## blake2b256

[BLAKE-256](https://en.wikipedia.org/wiki/BLAKE_%28hash_function%29) hash function.

```
blake2b256(bytes: ByteVector): ByteVector
```

### Parameters

#### `bytes`: ByteVector

The array of bytes to encode.


## keccak256

[SHA-3-256](https://en.wikipedia.org/wiki/SHA-3) hash function.

```
keccak256(bytes: ByteVector): ByteVector
```

### Parameters

#### `bytes`: ByteVector

The array of bytes to encode.


## sha256

[SHA-256](https://en.wikipedia.org/wiki/SHA-2) hash function.

```
sha256(bytes: ByteVector): ByteVector
```

### Parameters

#### `bytes`: ByteVector

The array of bytes to encode.


## toBase16String

Encodes an array of bytes to a [Base16](https://en.wikipedia.org/wiki/Hexadecimal) string.

```
toBase16String(bytes: ByteVector): String
```

### Parameters

#### `bytes`: ByteVector

The array of bytes to encode.



## toBase58String

Encodes an array of bytes to a [Base58](https://en.wikipedia.org/wiki/Base58) string.

```
toBase58String(bytes: ByteVector): String
```

### Parameters

#### `bytes`: ByteVector

The array of bytes to encode.


## toBase64String

Encodes an array of bytes to a [Base64](https://en.wikipedia.org/wiki/Base64) string.

```
toBase64String(bytes: ByteVector): String
```

### Parameters

#### `bytes`: ByteVector

The array of bytes to encode.

### addressFromString

Decodes address from [Base58](https://en.wikipedia.org/wiki/Base58) string.

```
addressFromString(string: String): Address|Unit
```

### Parameters

#### `string`: String

The string to decode.


## addressFromStringValue

Decodes address from [Base58](https://en.wikipedia.org/wiki/Base58) string.

Raises an exception if the string can not be parsed.

```
addressFromStringValue(string: String): Address
```

### Parameters

#### `string`: String

The string to decode.



## fromBase16String

Decodes a [Base16](https://en.wikipedia.org/wiki/Hexadecimal) string to an array of bytes.

```
fromBase16String(str: String): ByteVector
```

### Parameters

#### `str`: String

The string to decode.


## fromBase58String

Decodes a [Base58](https://en.wikipedia.org/wiki/Base58) string to an array of bytes.

```
fromBase58String(str: String): ByteVector
```

### Parameters

#### `str`: String

The string to decode.


## fromBase64String

Decodes a [Base64](https://en.wikipedia.org/wiki/Base64) string to an array of bytes.

```
fromBase64String(str: String): ByteVector
```

### Parameters

#### `str`: String

The string to decode.
