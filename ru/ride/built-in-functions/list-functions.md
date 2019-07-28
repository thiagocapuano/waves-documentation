# Функции списка

| # | Название | Описание | Сложность |
| :--- | :--- | :--- | :--- |
| 1 | [getElement(List[T], Int): T](#get-element)  | Получает элемент по индексу | 2 |
| 2 | [cons(T, List[T]): List[T]](#cons)  | Вставляет элемент в начало списка | 2 |
| 3 | [size(List[T]): Int](#size)  | Возвращает размер списка | 2 |

## getElement(List[T], Int): T<a id="get-element"></a>

Получает элемент по индексу.
``` ride
getElement(arr: List[T], pos: Int): T
```

### Параметры

#### `arr`: List[T]

Список.

#### `pos`: Int

Индекс элемента.

## cons(T, List[T]): List[T] <a id="cons"></a>

Вставляет элемент в начало списка.

``` ride
cons(head:T, tail: List[T]): List[T]
```

### Параметры

#### `head`: T

Элемент.

#### `tail`: List[T]

Список.

## size(List[T]): Int <a id="size"></a>

Возвращает размер списка.

``` ride
size(arr: List[T]): Int
```

### Параметры

#### `arr`: List[T]

Список.
