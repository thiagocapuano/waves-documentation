# Транзакция данных оракула Token Rating

Раз в сутки [оракул](/waves-oracles/oracle.md) [Token Rating](https://oracles.wavesexplorer.com/oracle/3P2eDV4pWJGmPjLGLrW4dsMA53te4gzkwnH) отправляет в блокчейн Waves [транзакцию данных](/blockchain/transaction-type/data-transaction.md) с рейтингами токенов, у которых за прошедшие 24 часа рейтинг менялся. В одну транзакцию данных входит не более 100 изменений, поэтому, если изменений будет больше, то будет отправлено несколько транзакций.

Пример поля `data` такой транзакции:

```js
"data": [
  {
    "key": "assetRating_62LyMjcr2DtiyF5yVXFhoQ2q414VPPJXjsNYp72SuDCH",
    "type": "string",
    "value": "4.5"
  }, {
    "key": "assetRating_4QUMfcxQB112bZdyoAPrp1oTVN4cBA68NpGkD7W3n33i",
    "type": "string",
    "value": "3.9"
  },
  ...
]
```

Значение поля `key` формируется конкатенацией строк:

```js
"assetRating_" + assetId
```

где

`"assetRating_"` — строковая константа,

`assetId` — идентификатор токена.