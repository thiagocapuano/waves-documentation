# Structures

All structures in RIDE are predefined — you cannot create your own structures.

All structures have constructors.

## Examples

The following code creates an instance of the `DataEntry` structure and reads its key and value:

```ride
{-# STDLIB_VERSION 3 #-}
{-# CONTENT_TYPE DAPP #-}

let data = DataEntry("Age", 33)
let key  = data.key
let val = data.value
```