# Transaction body bytes

The **transaction body** bytes are the bytes of all the fields of a [binary representation](/blockchain/transaction-data-structure.md) of a transaction with the exception of `id`, `signature` and `proofs` fields.

Based on the transaction body bytes, the transaction ID is generated.

Based on the transaction body bytes, the [transaction signature](/blockchain/transaction-signature.md) is created.
