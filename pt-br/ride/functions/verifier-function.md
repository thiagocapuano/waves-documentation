# Verifier function

A **verifier function** is a [function](/ride/functions.md) of a [dApp script](/ride/ride-script/dapp-script.md) that has `@Verifier` [annotation](/ride/annotations.md).

A verifier function is responsible for [validation of transactions](/blockchain/transaction-validation.md) and orders sent from [dApp](/blockchain/dapp.md).

A dApp script can have only _one_ verifier function.

A verifier function has no arguments.

## Example

``` ride
@Verifier(tx)
func verify() = {
    match tx {
        case _: Order|SetScriptTransaction =>
            sigVerify(tx.bodyBytes, tx.proofs[0], tx.senderPublicKey)
        case _ => false
    }
}
```
