# Set script transaction binary format

Sets the script which verifies all outgoing transactions. The set script can be changed by another.

| \# | Field name | Type | Length in Bytes |
| --- | --- | --- | --- |
| 1 | Transaction multiple version mark | Byte \(constant, value = 0\) | 1
| 2 | Transaction type | Byte \(constant, value = 13\) | 1
| 3 | Version | Byte | 1
| 4 | Chain ID | Byte | 1
| 5 | Sender's public key | PublicKey \(Array[Byte]\) | 32
| 6.1 | Script existence flag \(1/0\) |  | 1
| 6.2 | Script length \(S\) |  | 2 or 0 \(depends on the byte in 6.1\)
| 6.3 | Script | Script | S <= 32768 or 0 \(depends on the byte in 6.1\)
| 7 | Fee | Long | 8
| 8 | Timestamp | Long | 8
| 9 | Proofs | Proofs | See Proofs structure
