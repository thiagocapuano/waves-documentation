# Account data storage

An **account data storage** is an array of records of type `DataEntry` which is associated with an [account](/blockchain/account.md).

Each account has a _single_ account data storage.

## Adding records

Records are added to an account data storage using a [data transaction](/blockchain/transaction-type/data-transaction.md) or an invoke script transaction.

The number of records in the account data storage is unlimited.

The maximum size of a single record is 32 kilobytes.

The number of records that can be added to an account data storage within one transaction is limited: for a data transaction, it is 100.

## Editing records

The `key` and `value` fields of a record can be overwritten; the `key` field of a record cannot be overwritten.

## Deleting records

> A record from an account data storage cannot be deleted
