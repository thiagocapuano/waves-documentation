# Callable function

A **callable function** is a function of a [dApp script](/blockchain/dapp-script.md) that has `@Callable` [annotation](/ride/annotations.md).

A dApp script may have several callable functions.

A callable function of a [dApp](/blockchain/dapp.md) can be invoked by the invoke script transaction.

## Example

``` ride
@Callable(inv)
func rate(name: String, rating: Int) = {
    WriteSet([DataEntry(inv.caller.toString(), name + rating.toString()])
}
```
