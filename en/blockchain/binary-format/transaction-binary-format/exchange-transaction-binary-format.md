# Exchange transaction binary format

## Binary format version 1

| # | Field name | Type | Length in Bytes |
| --- | --- | --- | --- |
| 1 | Transaction type | Byte (constant, value = 7) | 1
| 2 | Buy order object length (BN) | Int | 4
| 3 | Sell order object length (SN) | Int | 4
| 4 | Buy order object | OrderV1 | BN, see OrderV1 structure
| 5 | Sell order object | OrderV1 | SN, see OrderV1 structure
| 6 | Price | Long | 8
| 7 | Amount | Long | 8
| 8 | Buy matcher fee | Long | 8
| 9 | Sell matcher fee | Long | 8
| 10 | Fee | Long | 8
| 11 | Timestamp | Long | 8
| 12 | Signature | ByteStr (Array[Byte]) | 64

The transaction's signature is calculated from the following bytes:

| # | Field name | Type | Length in Bytes |
| --- | --- | --- | --- |
| 1 | Transaction type | Byte (constant, value = 7) | 1
| 2 | Buy order object length (BN) | Int | 4
| 3 | Sell order object length (SN) | Int | 4
| 4 | Buy order object | OrderV1 | BN, see OrderV1 structure
| 5 | Sell order object | OrderV1 | SN, see OrderV1 structure
| 6 | Price | Long | 8 |
| 7 | Amount | Long | 8 |
| 8 | Buy matcher fee | Long | 8 |
| 9 | Sell matcher fee | Long | 8 |
| 10 | Fee | Long | 8 |
| 11 | Timestamp | Long | 8 |

## Binary format version 2

| # | Field name | Type | Length in Bytes |
| --- | --- | --- | --- |
| 1 | Transaction multiple version mark | Byte (constant, value = 0) | 1
| 2 | Transaction type | Byte (constant, value = 7\) | 1
| 3 | Version | Byte | 1
| 4.1 | Buy order size (BN) |  | 4
| 4.2 | Buy order version mark |  | 1 (version 1) / 0 (version 2)
| 4.3 | Buy order | Order | BN, see the appropriate Order version structure
| 5.1 | Sell order size (SN) |  | 4
| 5.2 | Sell order version mark |  | 1 (version 1) / 0 (version 2)
| 5.3 | Sell order | Order | SN, see the appropriate Order version structure
| 6 | Price | Long | 8
| 7 | Amount | Long | 8
| 8 | Buy matcher fee | Long | 8
| 9 | Sell matcher fee | Long | 8
| 10 | Fee | Long | 8
| 11 | Timestamp | Long | 8
| 12 | Proofs | Proofs | See Proofs structure
