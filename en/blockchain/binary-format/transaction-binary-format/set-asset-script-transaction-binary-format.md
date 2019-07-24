# Set asset script transaction binary format

| \# | Field name | Type | Length in Bytes |
| --- | --- | --- | --- |
| 1 | Transaction multiple version mark | Byte \(constant, value = 0\) | 1
| 2 | Transaction type | Byte \(constant, value = 15\) | 1
| 3 | Version | Byte | 1
| 4 | Chain ID | Byte | 1
| 5 | Sender's public key | PublicKey \(Array[Byte]\) | 32
| 6 | Asset ID | ByteStr \(Array[Byte]\) | 32
| 7 | Fee | Long | 8
| 8 | Timestamp | Long | 8
| 9.1 | Script existence flag \(1/0\) |  | 1
| 9.2 | Script length \(S\) |  | 2 or 0 \(depends on the byte in 9.1\)
| 9.3 | Script | Script | S <= 32768 or 0 \(depends on the byte in 9.1\)
| 10 | Proofs | Proofs | See Proofs structure

Below is a sample **Set Asset Script** encoded as **JSON**:

```cpp
{
    "type" : 15,
    "id" : "EXDKRNL5Apiw3K9mvLjPVNTWRhDwEvzeA9GAXSrYfQsh",
    "assetId" : "L5Apiw3K9mvLjPVNTWRhDwEvzeA9GAEXDKRNXSrYfQsh",
    "sender" : "3N9dfiTb8Pd6hqhvXaf8GcdTxdwCAeyxsvr",
    "senderPublicKey" : "6gT9PnyXA2sQ9AyRYn1QqkquWSu44Hr3qzLxszchTD1J",
    "fee" : 100000000,
    "timestamp" : 1535102049904,
    "proofs" : [ "4QwRFUNZUk7KaWGnmnYp6pUqUrLjZk3hFwhQTaJN7SUAYDvmXVkU4DDWadH5pQWkaUYiAdCQFtqSKZyKwyaUdyUN" ],
    "version" : 1,
    "script" : "base64:AQQAAAALYWxpY2FANpZ25lZAUAAAAJYm9iU2lnbmVkB5fCpHI"
}
```
