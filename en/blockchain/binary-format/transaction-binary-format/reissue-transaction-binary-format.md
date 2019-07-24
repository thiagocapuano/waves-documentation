# Reissue transaction binary format

## Binary format version 1

| \# | Field name | Type | Length in Bytes |
| --- | --- | --- | --- |
| 1 | Transaction type | Byte \(constant, value = 5\) | 1
| 2 | Signature | ByteStr \(Array[Byte]\) | 64
| 3 | Transaction type | Byte \(constant, value = 5\) | 1
| 4 | Sender's public key | PublicKey \(Array[Byte]\) | 32
| 5 | Asset ID | ByteStr \(Array[Byte]\) | 32
| 6 | Quantity | Long | 8
| 7 | Reissuable flag \(1 - True, 0 - False\) | Boolean | 1
| 8 | Fee | Long | 8
| 9 | Timestamp | Long | 8

The transaction's signature is calculated from the following bytes:

| \# | Field name | Type | Length in Bytes |
| --- | --- | --- | --- |
| 1 | Transaction type | Byte \(constant, value = 5\) | 1
| 2 | Sender's public key | PublicKey \(Array[Byte]\) | 32
| 3 | Asset ID | ByteStr \(Array[Byte]\) | 32
| 4 | Quantity | Long | 8 |
| 5 | Reissuable flag \(1 - True, 0 - False\) | Boolean | 1
| 6 | Fee | Long | 8 |
| 7 | Timestamp | Long | 8 |

## Binary format version 2

| \# | Field name | Type | Length in Bytes |
| --- | --- | --- | --- |
| 1 | Transaction multiple version mark | Byte \(constant, value = 0\) | 1
| 2 | Transaction type | Byte \(constant, value = 5\) | 1
| 3 | Version | Byte | 1
| 4 | Chain ID | Byte | 1
| 5 | Sender's public key | PublicKey \(Array[Byte]\) | 32
| 6 | Asset ID | ByteStr \(Array[Byte]\) | 32
| 7 | Quantity | Long | 8
| 8 | Reissuable flag \(1 - True, 0 - False\) | Boolean | 1
| 9 | Fee | Long | 8
| 10 | Timestamp | Long | 8
| 11 | Proofs | Proofs | See Proofs structure
