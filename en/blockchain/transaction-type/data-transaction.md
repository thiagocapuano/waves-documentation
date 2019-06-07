# Data transaction

**Data transaction** is a [transaction](/blockchain/transaction.md) that writes data to account data storage.

## Array data of a transaction

The maximum size of the array of data of a transaction is 140 kilobytes.

The maximum number of elements in the array of data is 100.

Each element of the array is an object that has 3 fields: `key`, `type`, `value`.

## The `key` field

The value of the `key` field is a UTF-8 encoded string of length from 0 to 100 characters inclusive.

## The `type` field

The value of the `type` field is a short integer that specifies the type of the data stored in the `value` field:

* 0 — integer
* 1 — boolean
* 2 — array of bytes
* 3 — string

## The `value` field

The `value` field can store an integer, a boolean, an array of bytes, or a string.

The size of the data of the field can be from 0 to 32767 bytes.

## Data structure

| Field order number | Field name | JSON field name  | Field Type | Field size in bytes | Field description |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | Version flag | | Byte | 1 | Indicates that the current transaction has [data structure](/blockchain/transaction-data-structure.md) of version 2 or above. The value must be 0 |
| 2 | Transaction type | type | Byte  | 1 | ID of the [transaction type](/blockchain/transaction-type.md). The value must be 12 |
| 3 | Version | version | Byte | 1 | Version number of the data structure of the transaction. The value must be 1 |
| 4 | Public key of sender | senderPublicKey | Array of bytes | 32 | Account public key of the sender |
| 5 | Data entries count | | Short | 2 | |
| 6.1 | 1st element’s key length | | Short | 2 | |
| 6.2 | 1st element’s key | key | String | 4 × `L` | `L` is a key length |
| 6.3 | 1st element’s data type | type | Byte | 1 | |
| 6.4 | 1st element’s data | value | The same as the data type has | Depends on the size of the data | |
| 6.5 | 2nd element’s key length | | Short | 2 | |
| 6.6 | 2nd element’s key | key | String | 4 × `L` | `L` is a key length |
| 6.7 | 2nd element’s data type | type | Byte | 1 | |
| 6.8 | 2nd element’s data | value | The same as the data type has | Depends on the size of the data | |
| ... | ... | ... | ... | ... | ... |
| ... | ... | ... | ... | ... | ... |
| ... | ... | ... | ... | ... | ... |
| ... | ... | ... | ... | ... | ... |
| 6.[4 × `N - 3`] | N-th element’s key length | | Short | 2 | |
| 6.[4 × `N - 2`] | N-th element’s  key | key | String | 4 × `L` | `L` is a key length |
| 6.[4 × `N - 1`] | N-th element’s data type | type | Byte | 1 | |
| 6.[4 × `N`] | N-th element’s data | value | The same as the data type has | Depends on the size of the data | |
| 7 | Timestamp | timestamp | Long | 8 | Unix time of sending of transaction to blockchain |
| 8 | Fee | fee | Long | 8 | [Transaction fee](/blockchain/transaction-fee.md) in [WAVELETs](/blockchain/token/wavelet.md) |
| 9 | Proofs | proofs | Array of [proofs](/blockchain/transaction-proof.md) | `S` | If the array is empty, then `S` = 3. If the array is not empty, then `S` = 3 + 2 × `N` + (`P1` + `P2` + ... + `P`<sub>`n`</sub>), where `N` is the number of proofs in the array, `P`<sub>`n`</sub> is the size of `N`-th proof in bytes. The maximum number of proofs in the array is 8. The maximum size of each proof is 64 bytes |

## JSON representation of a transaction

```json
{
   "type":12,
   "version":1,
   "senderPublicKey":"5AzfA9UfpWVYiwFwvdr77k6LWupSTGLb14b24oVdEpMM",
   "data":[
      {
         "key":"int",
         "type":"integer",
         "value":24
      },
      {
         "key":"isWeekend",
         "value":true,
         "type":"boolean"
      },
      {
         "key":"blob",
         "value":"base64:BzWHaQU",
         "type":"binary"
      },
      {
         "key":"My poem",
         "value":"Oh Waves!",
         "type":"string"
      }
   ],
   "timestamp":1520945679531,
   "fee":100000,
   "proofs":[
      "4huvVwtbALH9W2RQSF5h1XG6PFYLA6nvcAEgv79nVLW7myCysWST6t4wsCqhLCSGoc5zeLxG6MEHpcnB6DPy3XWr"
   ],
   "id":"CwHecsEjYemKR7wqRkgkZxGrb5UEfD8yvZpFF5wXm2Su",
   "sender":"3FjTpAg1VbmxSH39YWnfFukAUhxMqmKqTEZ",
   "height":303
}
```
