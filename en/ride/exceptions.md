#Exceptions

You can throw exceptions in RIDE using the `throw` function:
```
func main(amount: Int) = {
   if (amount > 0) then "done" else throw()
}
```
The return type of the `throw` function is [Nothing](/ride/data-types.md).

There is no exception handling in RIDE.
