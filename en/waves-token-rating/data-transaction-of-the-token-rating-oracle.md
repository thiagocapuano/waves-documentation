# Data transaction of the Token Rating oracle

Once a day, the [Token Rating](https://oracles.wavesexplorer.com/oracle/3P2eDV4pWJGmPjLGLrW4dsMA53te4gzkwnH) [oracle](/waves-oracles/oracle.md) sends to the Waves blockchain a [data transaction](/blockchain/transaction-type/data-transaction.md) with the token ratings, that have been changed in the past 24 hours. No more than 100 changes are included in one data transaction, therefore, if there are more changes, then several transactions will be sent.

An example of the `data` field of such a transaction:

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

The value of the `key` field is formed by concatenation of strings:

```js
"assetRating_" + tokenID
```

where

`"assetRating_"` is a string constant,

`tokenID` is the ID of the token.
