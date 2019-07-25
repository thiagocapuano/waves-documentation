# Callable function

A **callable function** is a [function](/ride/functions.md) of a [dApp script](/ride/ride-script/dapp-script.md) that has `@Callable` [annotation](/ride/annotations.md).

A dApp script may have several callable functions.

A callable function of a [dApp](/blockchain/dapp.md) can be invoked by the [invoke script transaction](/blockchain/transaction-type/invoke-script-transaction.md).

## Example

``` ride
@Callable(inv)
func rate(name: String, rating: Int) = {
    WriteSet([DataEntry(inv.caller.toString(), name + rating.toString()])
}
```
