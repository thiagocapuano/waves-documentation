# Transaction

A **transaction** is an action on the [blockchain](/blockchain.md) on behalf of an [account](/blockchain/account.md).

Transactions can be sent _only_ from an account: thus, any transaction can be associated with some account.

There are several [transaction types](/blockchain/transaction-type.md) on the Waves blockchain.

## Transaction ID

Each transaction has a unique ID.

**A transaction ID** is a hash of the [transaction body bytes](/blockchain/transaction-body-bytes.md) which is calculated with the [blake2b256](https://en.wikipedia.org/wiki/BLAKE_(hash_function)) hash function.
