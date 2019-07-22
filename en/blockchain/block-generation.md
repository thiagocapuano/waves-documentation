# Block generation

A **block generation** is a process of creation of new [blocks ](/blockchain/block.md) on the [blockchain](/blockchain/blockchain.md).

Blocks are generated by miners according to the [Waves-NG protocol](/blockchain/waves-protocol/waves-ng-protocol.md).

To generate a new block, the miner must validate all the transactions inside of each microblock.

One generated block can contain from 0 to 6000 [transactions](/blockchain/transaction.md).

## Average block generation time

Average block generation time indicates how much time it takes for miners to add new blocks of transactions to the blockchain.

The generation time is calculated by a special formula.

## Average block generation time formula

T= G / (P×B)

where

`T` is the block generation time in seconds fori-th account (30s &lt;= block generation time &lt;= 90s).

`G` is the generation signature.

`P` is the proportion of total mining power that thei-th account has and it depends on the account balance (the more balance a miner has, the more power to generate the next block).

`B` is the [base target](/blockchain/block-generation/base-target.md).