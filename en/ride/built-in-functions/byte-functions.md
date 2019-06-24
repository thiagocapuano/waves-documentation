# Byte functions

|Name | Description | Complexity |
| :--- | :--- | :--- |
| [drop(ByteVector, Int): ByteVector](#drop) | Drops the first `n` bytes of an array of bytes | 1 |
| [dropRight(ByteVector, Int): ByteVector](#drop-right) | Drops the last `n` bytes of an array of bytes | 19 |
| [size(ByteVector): Int](#size) | Returns the size of an array of bytes | 1 |
| [take(ByteVector, Int): ByteVector](#take) | Takes the first `n` bytes from an array of bytes | 1 |
| [takeRight(ByteVector, Int): ByteVector](#take-right) | Takes the last `n` bytes from an array of bytes | 19 |

## drop(ByteVector, Int): ByteVector<a id="drop"></a>

Drops the first `n` bytes of an array of bytes.

```
drop(xs: ByteVector, number: Int): ByteVector
```

### Parameters

#### `xs`: ByteVector

The array of bytes.

#### `number`: Int

The number of the first `n` bytes.

## dropRight(ByteVector, Int): ByteVector<a id="drop-right"></a>

Drops the last `n` bytes of an array of bytes.

```
dropRight(xs: ByteVector, number: Int): ByteVector
```

### Parameters

#### `xs`: ByteVector

The array of bytes.

#### `number`: Int

The number of thelast `n` bytes.

## size(ByteVector): Int<a id="size"></a>

Returns the size of an array of bytes.

```
size(byteVector: ByteVector): Int
```

### Parameters

#### `byteVector`: ByteVector

The array of bytes.

## take(ByteVector, Int): ByteVector<a id="take"></a>

Takes the first `n` bytes from an array of bytes.

```
take(xs: ByteVector, number: Int): ByteVector
```

### Parameters

#### `xs`: ByteVector

The array of bytes.

#### `number`: Int

The number of the first `n` bytes to return.

## takeRight(ByteVector, Int): ByteVector<a id="take-right"></a>

Takes the last `n` bytes from an array of bytes.

```
takeRight(xs: ByteVector, number: Int): ByteVector
```

### Parameters

#### `xs`: ByteVector

The array of bytes.

#### `number`: Int

The number of the last `n` bytes to return.
