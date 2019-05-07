# Транзакция данных оракула Token Rating
[Оракул Token Rating](https://oracles.wavesexplorer.com/oracle/Dqrh9Pok57XUTEEynpBKAUWRt5EUpSzpsGmo5cMnWynM) ежедневно отправляет в блокчейн Waves транзакцию данных с рейтингом токенов, у которых за прошедшие 24 часа рейтинг менялся. В одну транзакцию входит не более 100 изменений, поэтому, если изменений будет больше, то опубликуется несколько транзакций.

Транзакция данных оракула Token Rating состоит из массива ключей. Имя каждого ключа формируется конкатенацией строк:
```
"assetRating_" + assetId
```
где 

`"assetRating_"` — строковая константа,

`assetId` — идентификатор ассета.

Пример содержимого массива `data` транзакции данных оракула Token Rating:
```
{
    "key": "assetRating_62LyMjcr2DtiyF5yVXFhoQ2q414VPPJXjsNYp72SuDCH",
    "type": "string",
    "value": "4.5"
}, {
    "key": "assetRating_4QUMfcxQB112bZdyoAPrp1oTVN4cBA68NpGkD7W3n33i",
    "type": "string",
    "value": "3.9"
}
...
```

