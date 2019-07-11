# Data transaction of the Token Rating oracle

Once a day, the [Token Rating](https://oracles.wavesexplorer.com/oracle/3P2eDV4pWJGmPjLGLrW4dsMA53te4gzkwnH) [oracle](/waves-oracles/oracle.md) sends to the blockchain a [data transaction](/blockchain/transaction-type/data-transaction.md) with [ratings and rates](/waves-token-rating/rating-formula.md) of tokens.

A data transaction contains the information about tokens, that have been rated in the past 24 hours.

A single transaction contains the information about no more than 50 tokens —  if there are more rated tokens, then several transactions will be sent.

An example of a [data array](/blockchain/transaction-type/data-transaction.md) of such a transaction:

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

The `key` field is formed by [concatenating](https://en.wikipedia.org/wiki/Concatenation) a string "assetRating\_" or a "scoreBoard\_" and a string with the ID of a token.

The `value` field contains an [escaped string](https://en.wikipedia.org/wiki/Escape_character) with rates.

## An example

Let's say we have an escaped string with rates:

``` js
"{\"1\":{\"votes\":0,\"tokens\":0},\"2\":{\"votes\":0,\"tokens\":0},\"3\":{\"votes\":3,\"tokens\":545},\"4\":{\"votes\":0,\"tokens\":0},\"5\":{\"votes\":2,\"tokens\":3827}}"
```

Let's unescape that string:

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
}
```

It follows from the string that no one rated the token with one, two or four stars.

Three users rated the token with three stars. The sum of the weights [W<sub>n</sub>](/waves-token-rating/rating-formula.md) of those rates is 545.

Two users rated the token with five stars. The sum of the weights W<sub>n</sub> of those rates is 3827.
