# Data transaction

**Data transaction** is a [transaction](/blockchain/transaction.md) that writes data to account data storage.
> The next data transaction can overwrite the existing keys but not delete them. There is currently no planned way to clear the state of an account. The data transaction cannot contain multiple entries sharing the same key

## Array data of a transaction

The maximum length of the data array is 100 element.
The maximum size of the data array is 140 kilobytes.
Each element of the data array is an object that has 3 fields: `key`, `type`, `value`.

## The `key` field

The value of the `key` field is a UTF-8 encoded string of length from 1 to 100 characters inclusive.

## The type field

The type field specifies the type of the value field:

* 0 — integer
* 1 — boolean
* 2 — array of bytes
* 3 — string

| Value type | Value type ID | Value type size in bytes |
|------------|---------------|--------------------------|
| integer    | 0             | 8                        |
| boolean    | 1             | 0 = false <br> 1 = true       |
| binary     | 2             | Up to 4                  |
| string     | 3             | Up to 4                  |

## The `value` field

The size of value field can be from 0 to 32767 bytes.

## Data structure

| Field order number | Field name | JSON field name  | Field Type | Field size in bytes | Field description |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | Version flag | | Byte | 1 | Indicates that the current transaction has [data structure](/blockchain/transaction-data-structure.md) of version 2 or above. The value must be 0 |
| 2 | Transaction type | type | Byte  | 1 | ID of the [transaction type](/blockchain/transaction-type.md). The value must be 12 |
| 3 | Version | version | Byte | 1 | Version number of the data structure of the transaction. The value must be 1 |
| 4 | Public key of sender | senderPublicKey | Array of bytes | 32 | Account public key of the sender |
| 5 | Length of the data array | | Short | 2 | |
| 6.1 | Key 1 length | | Short | 2 | |
| 6.2 | Key 1 | key | String | 4 × `L` | `L` is a key length |
| 6.3 | Value 1 type | type | Byte | 1 | |
| 6.4 | Value 1 | value | Depends on value type | Depends on the size of value type | |
| 6.5 | Key 2 length | | Short | 2 | |
| 6.6 | Key 2 | key | String | 4 × `L` | `L` is a key length |
| 6.7 | Value 2 type | type | Byte | 1 | |
| 6.8 | Value 2 | value | Depends on value type | Depends on the size of value type | |
| ... | ... | ... | ... | ... | ... |
| ... | ... | ... | ... | ... | ... |
| ... | ... | ... | ... | ... | ... |
| ... | ... | ... | ... | ... | ... |
| 6.[4 × `N - 3`] | N-th key length | | Short | 2 | |
| 6.[4 × `N - 2`] | N-th key | key | String | 4 × `L` | `L` is a key length |
| 6.[4 × `N - 1`] | N-th value type | type | Byte | 1 | |
| 6.[4 × `N`] | N-th value | value | Depends on value type | Depends on the size of value type | |
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
