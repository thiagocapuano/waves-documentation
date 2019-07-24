# Mass transfer transaction binary format

| \# | Field name | Type | Length in Bytes |
| --- | --- | --- | --- |
| 1 | Transaction type | Byte \(constant, value = 11\) | 1
| 2 | Version | Byte \(constant, value = 1\) | 1
| 3 | Sender's public key | PublicKey \(Array[Byte]\) | 32
| 4.1 | Asset ID existence flag \(1/0\) |  | 1
| 4.2 | Asset ID | AssetId \(ByteStr = Array[Byte]\) | 32 or 0 \(depends on the byte in 4.1\)
| 5.1 | Number of transfers |  | 2
| 5.2 | Address or alias for transfer 1 | Address or Alias | Depends on the first byte \(1 - Address, 2 - Alias\)
| 5.3 | Amount for transfer 1 | Long | 8
| 5.4 | Address or alias for transfer 2 | Address or Alias | Depends on the first byte \(1 - Address, 2 - Alias\)
| 5.5 | Amount for transfer 2 | Long | 8
| ... | ... | ... | ... |
| 6 | Timestamp | Long | 8
| 7 | Fee | Long | 8
| 8.1 | Attachments length \(N\) |  | 2
| 8.2 | Attachments | Array[Byte] | N <= 140
| 9 | Proofs | Proofs | See Proofs structure

The transaction signature is calculated from the fields 1 to 8.2, i.e. proofs and signatures are not included.

**Note.** [**Here**](/blockchain/transaction-type/mass-transfer-transaction.md) you can find more details about Mass Transfer Transaction.

Below is a sample **Mass Transfer transaction** encoded as **JSON**:

```cpp
  {
  "type" : 11,
  "version" : 1,
  "id" : "BG7MQF8KffVU6MMbJW5xPowVQsohwJhfEJ4wSF8cWdC2",
  "sender" : "3HhQxe5kLwuTfE3psYcorrhogY4fCwz2BSh",
  "senderPublicKey" : "7eAkEXtFGRPQ9pxjhtcQtbH889n8xSPWuswKfW2v3iK4",
  "fee" : 200000,
  "timestamp" : 1518091313964,
  "proofs" : [ "4Ph6RpcPFfBhU2fx6JgcHLwBuYSpn..." ],   // see Proofs below
  "assetId" : null,
  "attachment" : "59QuUcqP6p",
  "transfers" : [ {
    "recipient" : "3HUQa6qtLhNvBJNyPV1pDRahbrcuQkaDQv2",
    "amount" : 100000000
  }, {
    "recipient" : "3HaAdZcCXAqhvFj113Gbe3Kww4rCGMUZaEZ",
    "amount" : 200000000
  },
  ...
  ]
}
```
