# Account data storage

An **account data storage** is a storage, associated with an [account](/blockchain/account.md),  of data records.

Each account has a _single_ account data storage.

The size of an account data storage is unlimited.

## An account data storage record

An **account data storage record** is a data record that has a key-value format.

The key is a unique string.

The value is the data of one of the types:

* string
* boolean
* integral
* array of bytes

## Adding records

Records are added to an account data storage using a [data transaction](/blockchain/transaction-type/data-transaction.md) or an invoke script transaction.

The maximum size of a single record is 32 kilobytes.

## Editing records

The value of a record can be rewritten using a data transaction or an invoke script transaction.

The key of a record cannot be rewritten.

## Deleting records

A record cannot be deleted from an account data storage, it is only possible to rewrite its value.
