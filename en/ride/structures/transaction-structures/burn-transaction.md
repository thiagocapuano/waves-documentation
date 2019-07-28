# BurnTransaction

Structure of a [burn transaction](/blockchain/transaction-type/burn-transaction.md).

## Constructor

``` ride
BurnTransaction(quantity: Int, assetId: ByteVector, id: ByteVector, fee: Int, timestamp: Int, version: Int, sender: Address, senderPublicKey: ByteVector, bodyBytes: ByteVector, proofs: List[ByteVector])
```

## Fields

| # | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | quantity | Int | Amount of the [token](/blockchain/token.md) to burn |
| 2 | assetId | ByteVector | [ID of the token](/blockchain/token.md#token-id) to burn |
| 3 | id | ByteVector | [Transaction ID](/blockchain/transaction.md#transaction-id) |
| 4 | fee | Int | [Transaction fee](/blockchain/transaction-fee.md) |
| 5 | timestamp | Int | [Unix-time](https://ru.wikipedia.org/wiki/Unix-время) when the transaction was sent to the blockchain |
| 6 | version | Int | [Burn transaction](/blockchain/transaction-type/burn-transaction.md) version |
| 7 | sender | Address | [Address](/blockchain/address.md) of the transaction sender |
| 8 | senderPublicKey | ByteVector | Public key of the transaction sender  |
| 9 | bodyBytes | ByteVector | [Transaction body bytes](/blockchain/transaction-body-bytes.md) |
| 10 | proofs | List[ByteVector] | Array of [proofs](/blockchain/transaction-proof.md) |
