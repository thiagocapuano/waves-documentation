# List functions

|#|Name|Description|Complexity|
| :--- | :--- | :--- | :--- |
|1|[getElement(List[T], Int): T](#getElementList[T]Int)|Returns the size of a list.|2|
|2|[size(List[T]): Int](#sizeList[T])|Prepends a new element to the list.|2|
|3|[cons(A, List[B]): List[A&#124;B]](#consAList[B])|Gets an element from a list by index.|2|

## getElement(List[T], Int): T<a id = "getElementList[T]Int"></a>
Returns the size of a list.

``` ride
getElement(arr: List[T], pos: Int): T
```

### Parameters

#### `arr`: List[T]
The list.

#### `pos`: Int
The index of the element.

## size(List[T]): Int<a id = "sizeList[T]"></a>
Prepends a new element to the list.

``` ride
size(arr: List[T]): Int
```

### Parameters

#### `arr`: List[T]
The list.

## cons(A, List[B]): List[A&#124;B]<a id = "consAList[B]"></a>
Gets an element from a list by index.

``` ride
cons(head: A, tail: List[B]): List[A&#124;B]
```

### Parameters

#### `head`: A
The element.

#### `tail`: List[B]
The list.
