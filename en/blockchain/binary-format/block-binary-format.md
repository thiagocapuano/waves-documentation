# Block binary format

## Binary format version 3

| # | Field name | Field type | Field size in bytes | Comments |
| :--- | :--- | :--- | :--- | :--- |
| 1 | Version of the binary format of the block | Byte | 0 | The value must be 3 |
| 2 | [Unix time](https://en.wikipedia.org/wiki/Unix_time) when the [block](/blockchain/block.md) was generated | Long | 1 | |
| 3 | [Block signature](/blockchain/block/block-signature.md) of the parent block | Array of bytes | 64 | |
| 4 | Base target | Long | 8 | |
| 5 | Generation signature | Array of bytes | 32 | |
| 6 | Number of [transactions](/blockchain/transaction.md) in the [block](/blockchain/block.md) | Integer | 4 | |
| 7.1 | Transaction 1 | Array of bytes | Up to 100 | Bytes of the first transaction.<br>See [transaction binary format](/blockchain/binary-format/transaction-binary-format.md) |
| 7.2 | Transaction 2 | Array of bytes | Up to 100 | Bytes of the second transaction.<br>See [transaction binary format](/blockchain/binary-format/transaction-binary-format.md) |
| ... | ... | ... | ... | ... |
| 7.[N] | Transaction N | Array of bytes | Up to 100 | Bytes of the N-th transaction<br>See [transaction binary format](/blockchain/binary-format/transaction-binary-format.md) |
| 8 | Public key of the miner | Array of bytes | 32 | |
| 9 | [Block signature](/blockchain/block/block-signature.md) | Array of bytes | 64 | | |
