# List functions

| # | Name | Description | Complexity |
| :--- | :--- | :--- | :--- |
| 1 | [getElement(List[T], Int): T](#get-element) | Gets the element by index | 2 |
| 2 | [cons(T, List[T]): List[T]](#cons) | Inserts the element at the beginning of the list | 2 |
| 3 | [size(List[T]): Int](#size) | Returns the size of the list | 2 |

## getElement(List[T], Int): T <a id="get-element"></a>

Gets the element by index.

``` ride
getElement(arr: List[T], pos: Int): T
```

### Parameters

#### `arr`: List[T]

List.

#### `pos`: Int

Index of the element.

## cons(T, List[T]): List[T] <a id="cons"></a>

Inserts the element at the beginning of the list.

``` ride
cons(head:T, tail: List[T]): List[T]
```

### Parameters

#### `head`: T

Element.

#### `tail`: List[T]

List.

## size(List[T]): Int <a id="size"></a>

Returns the size of the list.

``` ride
size(arr: List[T]): Int
```

### Parameters

#### `arr`: List[T]

List.
