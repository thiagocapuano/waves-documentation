# Token Rating's oracle data transaction

[Token Rating's oracle](https://oracles.wavesexplorer.com/oracle/Dqrh9Pok57XUTEEynpBKAUWRt5EUpSzpsGmo5cMnWynM) daily sends to the Waves blockchain a data transaction with a rating of tokens whose rating has changed over the past 24 hours. No more than 100 changes are included in a single transaction, therefore, if there are more changes, several transactions will be sent. The `data` field of a transaction is an array of key-value pairs. The name of each key is formed by concatenation of strings:

```
"assetRating_" + assetId
```
where

`"assetRating_"` is a string constant,

`assetId` is the identifier of the asset.

An example of the contents of the `data` field serialized in JSON:

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