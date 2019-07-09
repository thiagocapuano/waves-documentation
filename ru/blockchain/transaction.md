# Транзакция

**Транзакция** — действие на [блокчейне](/blockchain/blockchain.md) от имени [аккаунта](/blockchain/account.md).

Транзакции можно отправлять _только_ с аккаунта — таким образом, любую транзакцию можно соотнести с каким-либо аккаунтом.

На блокчейне Waves существует несколько [типов транзакций](/blockchain/transaction-type.md).

## ID транзакции <a id="transaction-id"></a>

У каждой транзакции есть уникальный ID.

**ID транзакции** — хеш от [байтов тела транзакции](/blockchain/transaction-body-bytes.md), который вычисляется хеш-функцией [blake2b256](https://en.wikipedia.org/wiki/BLAKE_(hash_function)).

В отличие от остальных типов транзакций, ID [транзакции создания псевдонима](/blockchain/transaction-type/alias-transaction.md) рассчитывается как хеш от значений полей `type` и `alias`.
