# Exceptions

You can throw exceptions in RIDE using the `throw` function:
```
func main(amount: Int) = {
   if (amount > 0) then "done" else throw()
}
```
The return type of the `throw` is [Nothing](/ride/data-types.md).

There is no exception handling in RIDE. After the exception has been thrown, the script will stop its execution. The transaction will be considered as failed and will not be included in the block.
