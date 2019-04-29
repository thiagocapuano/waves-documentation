# Burn transaction

## Usage

Burn transaction is used to give the ability to burn tokens of an asset by specifying the amount and the asset id.

> \[!NOTE\]  
> Check the required [transaction fees ](/waves-blockchain/waves-transactions/transactions-fees.md)for the minimal fee in WAVES.

## Binary data structure

### Burn transaction version2

| \# | Field name | Type | Size in bytes |
| :--- | :--- | :--- | :--- |
| 1 | Transaction multiple version mark | Byte \(constant, value = 0\) | 1 |
| 2 | Transaction type | Byte \(constant, value = 6\) | 1 |
| 3 | Version | Byte | 1 |
| 4 | Chain ID | Byte | 1 |
| 5 | Sender's public key | PublicKey \(Array\[Byte\]\) | 32 |
| 6 | Asset ID | ByteStr \(Array\[Byte\]\) | 32 |
| 7 | Quantity | Long | 8 |
| 8 | Fee | Long | 8 |
| 9 | Timestamp | Long | 8 |
| 10 | Proofs | Proofs | See Proofs structure |

### Burn transaction version1

| \# | Field name | Type | Size in bytes |
| :--- | :--- | :--- | :--- |
| 1 | Transaction type | Byte \(constant, value = 6\) | 1 |
| 2 | Sender's public key | PublicKey \(Array\[Byte\]\) | 32 |
| 3 | Asset ID | ByteStr \(Array\[Byte\]\) | 32 |
| 4 | Quantity | Long | 8 |
| 5 | Fee | Long | 8 |
| 6 | Timestamp | Long | 8 |
| 7 | Signature | ByteStr \(Array\[Byte\]\) | 64 |

The transaction's signature is calculated from the following bytes:

| \# | Field name | Type | Length in bytes |
| :--- | :--- | :--- | :--- |
| 1 | Transaction type | Byte \(constant, value = 6\) | 1 |
| 2 | Sender's public key | PublicKey \(Array\[Byte\]\) | 32 |
| 3 | Asset ID | ByteStr \(Array\[Byte\]\) | 32 |
| 4 | Quantity | Long | 8 |
| 5 | Fee | Long | 8 |
| 6 | Timestamp | Long | 8 |

## JSON example

```js
{
"type":6,
"id":"csr25XQHT1c965Fg7cY2vJ7XHYVsudPYrUbdaFqgaqL",
"sender":"3P9QZNrHbyxXj8P9VrJZmVu2euodNtA11UW",
"senderPublicKey":"9GaQj7gktEiiS1TTTjGbVjU9bva3AbCiawZ11qFZenBX",
"fee":100000,
"timestamp":1548660675277,
"proofs":["61jCivdv3KTuTY6QHgxt4jaGrXcszWg3vb9TmUR26xv7mjWWwjyqs7X5VDUs9c2ksndaPogmdunHDdjWCuG1GGhh"],
"version":2,
"assetId":"FVxhjrxZYTFCa9Bd4JYhRqXTjwKuhYbSAbD2DWhsGidQ",
"amount":9999,
"chainId":87,
"height":1370971
}
```

The transaction example on Waves Explorer can be found [here](https://wavesexplorer.com/tx/csr25XQHT1c965Fg7cY2vJ7XHYVsudPYrUbdaFqgaqL).

