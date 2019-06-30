# Функции строки

| # | Название | Описание | Сложность |
| :--- | :--- | :--- | :--- |
| 1 | [drop(String, Int): String](#drop)  | Удаляет первые `n` символов строки | 1 |
| 2 | [dropRight(String, Int): String](#drop-right)  | Удаляет последние `n` символов строки | 19 |
| 3 | [indexOf(String, String): Int&#124;Unit](#index-of-first)  | Возвращает индекс первого вхождения подстроки  | 20 |
| 4 | [indexOf(String, String, Int): Int&#124;Unit](#index-after-index)  | Возвращает индекс первого вхождения подстроки после указанного индекса | 20 |
| 5 | [size(String): Int](#size)  | Возвращает длину строки | 1 |
| 6 | [split(String, String): List[String]](#split)  | Разбивает строку на список подстрок, используя разделитель | 100 |
| 7 | [take(String, Int): String](#take)  | Возвращает первые `n` символов строки | 1 |
| 8 | [takeRight(String, Int): String](#take-right)  | Возвращает последние `n` символов строки | 19 |

## drop(String, Int): String<a id=drop></a>

Удаляет первые `n` символов строки.

``` ride
drop(xs: String, number: Int): String
```

### Параметры

#### `xs`: String

Строка.

#### `number`: Int

Число `n`.

## dropRight(String, Int): String<a id=drop-right></a>

Удаляет последние `n` символов строки.

``` ride
dropRight(xs: String, number: Int): String
```

### Параметры

#### `xs`: String

Строка.

#### `number`: Int

Число `n`.

## indexOf(String, String): Int&#124;Unit<a id=index-of></a>

Возвращает индекс первого вхождения подстроки.

``` ride
indexOf(str: String, substr: String): Int|Unit
```

### Параметры

#### `str`: String

Строка.

#### `substr`: String

Подстрока.

## indexOf(String, String, Int): Int&#124;Unit<a id=index-of></a>

Возвращает индекс первого вхождения подстроки после указанного индекса.

``` ride
indexOf(str: String, substr: String, offset: Int): Int|Unit
```

### Параметры

#### `str`: String

Строка.

#### `substr`: String

Подстрока.

#### `offset`: Int

Индекс.

## size(String): Int<a id=size></a>

Возвращает длину строки.

``` ride
size(xs: String): Int
```

### Параметры

#### `xs`: String

Строка.

## split(String, String): List[String]<a id=split></a>

Разбивает строку на список подстрок, используя разделитель.

``` ride
split(str: String, separator: String): List[String]
```

### Параметры

#### `str`: String

Строка.

#### `separator`: Int

Разделитель.

## take(String, Int): String<a id=take></a>

Возвращает первые n символов строки.

``` ride
take(xs: String, number: Int): String
```

### Параметры

#### `xs`: String

Строка.

#### `number`: Int

Число `n`.

## takeRight(String, Int): String<a id=take-right></a>

Возвращает последние `n` символов строки.

``` ride
takeRight(xs: String, number: Int): String
```

### Параметры

#### `xs`: String

Строка.

#### `number`: Int

Число `n`.
