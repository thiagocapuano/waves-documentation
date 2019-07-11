# Functions

A function must return a value. The return type is not specified in the signature of a function.

A function must be declared above the place of its usage.

A function can be [annotated](/ride/annotations.md).

There are multiple [built-in functions](/ride/built-in-functions/built-in-functions.md) in RIDE.

## Examples

Definition of the function with no parameters that returns an integer:

``` ride
func main() = {
   3
}
```

Definition of a function with two parameters:

``` ride
func main(amount: Int, name: String) = {
   throw()
}
```
