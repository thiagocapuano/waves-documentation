## Facts about RIDE structures

* At the present moment, all structures in RIDE are predefined, therefore you can't create your own structures.
* All structures have constructors.

## Examples

The following code creates an instance of the `DataEntry` structure and reads its key and value:
```
{-# STDLIB_VERSION 3 #-}
{-# CONTENT_TYPE DAPP #-}
 
let data = DataEntry("k", 33)
let key  = data.key
let val = data.value
```

