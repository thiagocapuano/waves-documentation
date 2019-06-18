# Math functions

| Name | Description | complexity |
| :--- | :--- | :--- |
|[log(Int, Int, Int, Int, Int, Union): Int](#log(Int, Int, Int, Int, Int, Union) | Returns the logarithm of a number | 100 |
| [pow(Int, Int, Int, Int, Int, Union): Int](#pow(Int, Int, Int, Int, Int, Union) | Returns a number raised to a power | 100 |

## log(Int, Int, Int, Int, Int, Union): Int

Returns the logarithm of a number.

```
log(value: Int, ep: Int, base: Int, bp: Int, rp: Int, round: Union): Int
```

### Parameters

#### `value`: Int

The number which logarithm should be calculated.

#### `ep`: Int

The number of decimals of the number.

#### `base`: Int

The base of the logarithm.

#### `bp`: Int

The number of decimals of the base.

#### `rp`: Int

The number of decimals of the resulting value.

#### `round`: Union

[Rounding functions](#rounding-functions).

## Rounding functions

You can use rounding functions only with log and pow functions, i.e. you can not use them by themselves separately.


|Name | Description |
| :--- | :--- |
| Ceiling\(\): Int | Round towards positive infinity |
| Down\(\): Int | Round towards zero |
| Floor\(\): Int | Round towards negative infinity |
| HalfDown\(\): Int | Round down towards the nearest integer.If the discarded fraction is &gt; 0.5 then behaves as `Up()` |
| HalfEven\(\): Int | Round towards the nearest even neighbour.If the digit to the left of the discarded fraction is odd then behaves as`HalfUp()` otherwise behaves as `HalfDown()` |
| HalfUp\(\): Int | Round up towards the nearest neighbour.If the discarded fraction is &lt; 0.5 then behaves as `Down()` |
| Up\(\): Int | Round away from zero |

### Examples

| | -1.6 | -1.5 | -1.4 | -1.0 | 1.0 | 1.4 | 1.5 | 1.6 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Ceiling | -1 | -1 | -1 | -1 | 1 | 2 | 2 | 2 |
| Down | -1 | -1 | -1 | -1 | 1 | 1 | 1 | 1 |
| Floor | -2 | -2 | -2 | -1 | 1 | 1 | 1 | 1 |
| HalfDown | -2 | -1 | -1 | -1 | 1 | 1 | 1 | 2 |
| HalfEven | -2 | -2 | -1 | -1 | 1 | 1 | 2 | 2 |
| HalfUp | -2 | -2 | -1 | -1 | 1 | 1 | 2 | 2 |
| Up | -2 | -2 | -2 | -1 | 1 | 2 | 2 | 2 |
