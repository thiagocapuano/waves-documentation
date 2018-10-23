In this section, you can find all transactions body bytes details and the new fields which are included in the updated version of our transactions \(Version 2\) so you can compare it with the older version 1.

# Issue Transaction

| Field | Type | Length | Transaction Version1 | Transaction version2 |
| :--- | :--- | :--- | :--- | :--- |
| Transaction Type | Byte | 1 | + | + |
| Version | Byte | 1 | - | + |
| ChainId | Byte | 1 | - | + |
| Sender's Public Key | PublicKeyAccount | 32 | + | + |
| Name | Bytes | maximum N | + | + |
| Description | Bytes | maximum N | + | + |
| Quantity | Long | 8 | + | + |
| Decimals | Byte | 1 | + | + |
| Reissuable | Byte | 1 | + | + |
| Fee | Long | 8 | + | + |
| Timestamp | Long | 8 | + | + |
| Script |  |  | - | + |
| Proofs |  |  | - | + |
| Signature | Bytes | 64 | + | - |

# Reissue Transaction

| Field | Type | Length | Transaction Version1 | Transaction version2 |
| :--- | :--- | :--- | :--- | :--- |
| transactionType | Byte | 1 | + | + |
| version | Byte | 1 | - | + |
| chainId | Byte | 1 | - | + |
| Sender's Public Key | PublicKeyAccount | 32 | + | + |
| Asset ID | Bytes | 32 | + | + |
| Quantity  | Long | 8 | + | + |
| Reissuable | Boolean | 1 | + | + |
| Fee | Long | 8 | + | + |
| Timestamp | Long | 8 | + | + |
| Proofs |  |  | - | - |
| Signature | Bytes | 64 | + | - |


