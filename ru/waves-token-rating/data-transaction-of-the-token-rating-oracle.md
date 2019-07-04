# Транзакция данных оракула Token Rating

Раз в сутки [оракул](/waves-oracles/oracle.md) [Token Rating](https://oracles.wavesexplorer.com/oracle/3P2eDV4pWJGmPjLGLrW4dsMA53te4gzkwnH) отправляет в блокчейн [транзакцию данных](/blockchain/transaction-type/data-transaction.md) с [рейтингами и оценками](/waves-token-rating/rating-formula.md) токенов.

Транзакция данных содержит информацию о токенах, которые за прошедшие 24 часа были оценены.

Одна транзакция содержит информацию не более чем о 50 токенах — если оцененных токенов будет больше, то будет отправлено несколько транзакций.

Пример [массива данных](/blockchain/transaction-type/data-transaction.md) такой транзакции:

``` js
"data": [
  {
    "key": "assetRating_23g8VstaVP9bWcoYJtMUJ1HJk8FZkwcVaQ7d9trhfssY"
    "type": "string",
    "value": "4.3",
  },
  {
    "key": "scoreBoard_23g8VstaVP9bWcoYJtMUJ1HJk8FZkwcVaQ7d9trhfssY"
    "type": "string",
    "value": "{\"1\":{\"votes\":0,\"tokens\":0},\"2\":{\"votes\":1,\"tokens\":322},\"3\":{\"votes\":0,\"tokens\":0},\"4\":{\"votes\":0,\"tokens\":0},\"5\":{\"votes\":1,\"tokens\":1120}}",
  },
  {
    "key": "assetRating_E8gDQh5aDz6VQMwmFhUrpMERorwje6AqNe4FcjGSCNo6"
    "type": "string",
    "value": "5",
  },
  {
    "key": "scoreBoard_E8gDQh5aDz6VQMwmFhUrpMERorwje6AqNe4FcjGSCNo6"
    "type": "string",
    "value": "{\"1\":{\"votes\":0,\"tokens\":0},\"2\":{\"votes\":0,\"tokens\":0},\"3\":{\"votes\":0,\"tokens\":0},\"4\":{\"votes\":0,\"tokens\":0},\"5\":{\"votes\":1,\"tokens\":2827}}",
  }
  ...
]
```

Поле `key` формируется с помощью [конкатенации](https://ru.wikipedia.org/wiki/Конкатенация) строки "assetRating\_" или "scoreBoard\_" и строки с ID токена.

Поле `value` содержит [экранированную строку](https://ru.wikipedia.org/wiki/Экранирование_символов) с оценками.

## Пример

Предположим, имеется экранированная строка с оценками:

 ``` js
 "{\"1\":{\"votes\":0,\"tokens\":0},\"2\":{\"votes\":0,\"tokens\":0},\"3\":{\"votes\":3,\"tokens\":545},\"4\":{\"votes\":0,\"tokens\":0},\"5\":{\"votes\":2,\"tokens\":3827}}"
 ```

Разэкранируем данную строку:

``` js
{
  "1": {
    "votes": 0,
    "tokens": 0
  },
  "2": {
    "votes": 0,
    "tokens": 0
  },
  "3": {
    "votes": 3,
    "tokens": 545
  },
  "4": {
    "votes": 0,
    "tokens": 0
  },
  "5": {
    "votes": 2,
    "tokens": 3827
  }
```

Из строки следует, что никто не оценил токен одной, двумя или четырьмя звездами.

Три пользователя оценили токен тремя звездами. Сумма [весов W<sub>n</sub>](/waves-token-rating/rating-formula.md) этих оценок равна 545.

Два пользователя оценили токен пятью звездами. Сумма весов Wn этих оценок равна 3827.
