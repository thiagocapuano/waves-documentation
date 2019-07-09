# Transaction

A **transaction** is an action on the [blockchain](/blockchain.md) on behalf of an [account](/blockchain/account.md).

Transactions can be sent _only_ from an account — thus, any transaction can be associated with some account.

There are several [transaction types](/blockchain/transaction-type.md) on the Waves blockchain.

## Transaction ID <a id="transaction-id"></a>

Each transaction has a unique ID.

A **transaction ID** is a hash of the [transaction body bytes](/blockchain/transaction-body-bytes.md) which is calculated by the [blake2b256](https://en.wikipedia.org/wiki/BLAKE_(hash_function)) hash function.

Unlike the other transaction types, the transaction ID of an [alias transaction](/blockchain/transaction-type/alias-transaction.md) is calculated as a hash of the values of `type` and `alias` fields.
