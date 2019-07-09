# Вызываемая функция

**Вызываемая функция** — функция [dApp-скрипта](/blockchain/dapp-script.md) с аннотацией [@Callable](/ru/ride/annotations.md).

## Пример

``` ride
@Callable(inv)
func rate(name: String, rating: Int) = {
    WriteSet([DataEntry(inv.caller.toString(), name + rating.toString()])
}
```

dApp-скрипт может иметь несколько вызываемых функций.

Вызываемую функцию у [dApp](/blockchain/dapp.md) можно вызвать с помощью транзакции вызова скрипта.
