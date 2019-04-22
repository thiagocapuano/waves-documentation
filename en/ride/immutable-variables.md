# Immutable variables
In RIDE language _all_ variables are immutable. This means that as soon as we assign a value to a variable, it's not possible to change its value in the future. Variables in RIDE work as constant variables in major programming languages.

**let** is a keyword, that assigns a value to a variable in a lazy way (the word `let` works like [lazy val](https://docs.scala-lang.org/sips/improved-lazy-val-initialization.html) in Scala language).

The value of the variable, which was defined with the `let` word, will be calculated only in the moment of its first usage. Imagine we have the following RIDE script:
```
let a = 8
let b = a + 1
true
```
As we can see, the script returns `true`. Despite the fact that the variable `a` is used in line 2 for defining the variable `b`, the values of variables `a` and `b` will not be calculated during the script execution because the variable `b` is not used anywhere in the code.
## Examples
Integer value assignment:
```
let a = 8
```
String value assignment:
```
let b = "hello"
```
ByteVector value assignment:
```
let c = base58'5AzfA9UfpWVYiwFwvdr77k6LWupSTGLb14b24oVdEpMM'
```