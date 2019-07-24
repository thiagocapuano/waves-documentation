# Network message binary format

All network messages shares the same structure except the Handshake.

| \# | Field name | Type | Length in Bytes |
| --- | --- | --- | --- |
| 1 | Packet length \(BigEndian\) | Int | 4 |
| 2 | Magic Bytes | Bytes | 4 |
| 3 | Content ID | Byte | 1 |
| 4 | Payload length | Int | 4 |
| 5 | Payload checksum | Bytes | 4 |
| 6 | Payload | Bytes | N |

Magic Bytes are 0x12, 0x34, 0x56, 0x78. Payload checksum is first 4 bytes of \_FastHash\_ of Payload bytes. FastHash is hash function Blake2b256\(data\).
