# Transaction proof

A **transaction proof** is an array of bytes that can be used to check the validity of a transaction.

An array of proofs can consist of multiple [transaction signatures](/blockchain/transaction-signature.md) (but not limited to only signatures).

One of the examples of proofs usage is multisignature where it's important to store transaction signatures from different users in proofs.

Transactions with [data structures](/blockchain/transaction-data-structure.md)  of versions 2 and above are signed by proofs instead of signatures.  

## The data structure of an array of proofs

| Field order number | Field name | Field type | Field size in bytes | Field description |
| :--- | :--- | :--- | :--- | :--- |
| 1 | Proofs version | Byte | 1 | A special technical marker which determines the format of the array of proofs. <br>The value must be 0 |
| 2 | Proofs count | Short | 2 | Number of proofs in the array of proofs |
| 3 | Proof 1 length | Short | 2 | Length in bytes of the first proof |
| 4 | Proof 1 bytes | Array of bytes | up to 64 | Array of bytes of the first proof |
| 5 | Proof 2 length | Short | 2 | Length in bytes of the second proof |
| 6 | Proof 2 bytes | Array of bytes | up to 64 | Array of bytes of the second proof |
| ... | ... | ... | ... | ... |
