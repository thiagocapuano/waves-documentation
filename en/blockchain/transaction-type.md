# Transaction type

There are 15 types of transactions on the Waves blockchain:

| Transaction type name | Transaction type ID | Description |
| :--- | :--- | :--- |
| Genesis transaction | 1 |  |
| Issue transaction | 3 |  |
| Transfer transaction | 4 |  |
| Reissue transaction | 5 |  |
| Burn transaction | 6 |  |
| Exchange transaction | 7 |  |
| Lease transaction | 8 |  |
| Lease cancel transaction | 9 |  |
| Alias transaction | 10 |  |
| Mass transfer transaction | 11 |  |
| Data transaction | 12 |  |
| Set script transaction | 13 |  |
| Sponsorship transaction | 14 |  |
| Set asset script transaction | 15 |  |
| Invoke script transaction | 16 | Is not yet activated on the Waves mainnet. Only available on the Waves testnet. |

There are two versions of transactions which are _version1_ and _version2_. In the new version\(v2\), the transactions are signed by _proofs \_instead of using a signature. So basically \_signature is replaced with proofs \_to make API more consistent and flexible, all transactions will have \_version \_field and use \_proofs_. _Proofs_ are an alternative way to authorize the transaction that is more flexible than signatures and to enable smart contracts such as multisignature and atomic swap. Each proof is a _Base58_ encoded byte string and can be a signature, a secret, or anything else. The semantics of a proof is dictated by the smart contract that interprets it. There can be up to 8 proofs at most 64 bytes each.

