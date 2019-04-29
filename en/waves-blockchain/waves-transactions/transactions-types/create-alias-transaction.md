# Create alias transaction

## Usage

Create alias transaction is used to create an alias for an account.

> \[!NOTE\]  
> Check the required [transaction fees ](/waves-blockchain/waves-transactions/transactions-fees.md)for the minimal fee in WAVES.

## Binary data structure

### Burn transaction version2

| \# | Field name | Type | Size in bytes |
| :--- | :--- | :--- | :--- |
| 1 | Transaction multiple version mark | Byte \(constant, value = 0\) | 1 |
| 2 | Transaction type | Byte \(constant, value = 10\) | 1 |
| 3 | Version | Byte | 1 |
| 4 | Sender's public key | PublicKey \(Array\[Byte\]\) | 32 |
| 5.1 | Alias object length \(A\) |   | 2 |
| 5.2 | Alias object | Alias | 4 &lt;= A &lt;= 30 |
| 6 | Fee | Long | 8 |
| 7 | Timestamp | Long | 8 |
| 8 | Proofs | Proofs | See proofs structure |

### Burn transaction version1

| \# | Field name | Type | Size in bytes |
| :--- | :--- | :--- | :--- |
| 1 | Transaction type | Byte \(constant, value = 10\) | 1 |
| 2 | Sender's public key | PublicKey \(Array\[Byte\]\) | 32 |
| 3.1 | Alias object length \(A\) |   | 2 |
| 3.2 | Alias object | Alias | 4 &lt;= A &lt;= 30 |
| 4 | Fee | Long | 8 |
| 5 | Timestamp | Long | 8 |
| 6 | Signature | ByteStr \(Array\[Byte\]\) | 64 |

The transaction's signature is calculated from the following bytes:

| \# | Field name | Type | Size in bytes |
| :--- | :--- | :--- | :--- |
| 1 | Transaction type | Byte \(constant, value = 10\) | 1 |
| 2 | Sender's public key | PublicKey \(Array\[Byte\]\) | 32 |
| 3.1 | Alias object length \(A\) |   | 2 |
| 3.2 | Alias object | Alias | 4 &lt;= A &lt;= 30 |
| 4 | Fee | Long | 8 |
| 5 | Timestamp | Long | 8 |

## JSON example

```js
{
"type":10,
"id":"5CZV9RouJs7uaRkZY741WDy9zV69npX1FTZqxo5fsryL",
"sender":"3PNaua1fMrQm4TArqeTuakmY1u985CgMRk6",
"senderPublicKey":"B3f8VFh6T2NGT26U7rHk2grAxn5zi9iLkg4V9uxG6C8q",
"fee":100000,
"timestamp":1548666019772,
"proofs":["3cUM8Eq5KfmbS6q1qHDfzhX98YzER1ocnVjVAHG9HSkQdw86zjqxUfmsUPVwnVgwu5zatt3ETLnNFteobRMyR8bY"],
"version":2,
"alias":"2.1.0a",
"height":1371063
}
```

The transaction example on Waves Explorer can be found [here](https://wavesexplorer.com/tx/5CZV9RouJs7uaRkZY741WDy9zV69npX1FTZqxo5fsryL).

