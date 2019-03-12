# Ride4DApps

The main goal is to enable classic _**'DApps'**_ approach on Waves by adding the ability to define functions in a contract. Upon contract invocation, the state/payments are made according to what function states to do and does it automatically.

## Functions Types

In RIDE4DApps, we introduce two types of functions: Callable functions and Verifier function.

### Verifier Function

It works exactly like current ride script\(which is an expression that returns a BOOLEAN\) as following:

```js
@Verifier(tx)
func verify() = {
   let a = ...
   let b = ...
   (a || b) && sigVerify(tx...)
}
```

{% prettyhint type="info" %} tx is no longer part of global context, but the actual transaction object is bound through @Verifier annotation. {% endprettyhint %}

### **Callable Functions**

Callable functions are the functions which are defined inside ride script, and can be invoked through _**ContractInvocationTransaction**_. _**ContractInvocationTransaction**_ is a new transaction type that allows to invoke a function of a contract, to pass arguments and additional payment for a contract. For accessing the data of an invoked function \(such as getting how many waves/tokens were attached\), You need to use _**@Callable\(inv\)**_ binding where the parameter _**inv**_ is of type _**Invocation**_. Basically _**Invocation**_ is a data structure of:

* caller: Address.
* contractAddress: Address.
* payment: Payment\|Un, where Payment consist of amount: Long and assetId: ByteVector \| Unit.

Unlike verifier function, _**Callable function**_ can return one of: 

* _**WriteSet,**_ It's a keyValue list which defines what data will be stored in contract's account upon contract invocation.
* _**TransferSet,**_ It's a keyValue list which defines what outgoing payments will be made upon contract invocation.
* _**ContractResult, **_It's_** **_the combination of WriteSet and TransferSet.











