#Исключения
Исключения в RIDE выбрасываются с помощью функции `throw`:
```
func main(amount: Int) = {
   if(amount > 0) then "done" else throw()
}
```
Функция `throw` имеет возвращаемый тип [Nothing](/ride/data-types.md).

В RIDE нет обработки исключений.