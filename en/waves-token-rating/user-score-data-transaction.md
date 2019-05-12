# User score data transaction
When a user has scored a token, a data transaction is formed. The `data` field of this transaction is an array of key-value pairs:

| Key name | Value data type | The presence of the key-value pair is required | Description |
|---|---|:-:|---|
| tokenRating | String  | Yes | Allows to find user score data transactions in the Waves Token Rating |
| assetId | String  | Yes | Token identifier |
| score  |  Integer | Yes | User score |



An example of the contents of the `data` field serialized in JSON:
```
{
    "key": "tokenRating",
    "type": "string",
    "value": "tokenRating"
}, {
    "key": "assetId",
    "type": "string",
    "value": "BrjUWjndUanm5VsJkbUip8VRYy6LWJePtxya3FNv4TQa"
}, {
    "key": "score",
    "type": "integer",
    "value": 4
}
```