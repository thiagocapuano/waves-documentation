# About Waves Token Rating

**Waves Token Rating** is an online service (https://tokenrating.wavesexplorer.com) that shows the ratings of tokens (projects) issued on the Waves Platform.

Ratings of tokens are based on the opinions of community members. Only WCT token holders can participate in voting for tokens.

## Service user interface overview

See the page [Waves Token Rating user interface overview](/waves-token-rating/waves-token-rating-user-interface-overview.md).

## Voting restrictions

Tokens can only be scored from desktop versions of browsers. For mobile versions of browsers, the service is available only for viewing.

The voting process for any token can be initiated by any user, provided that the Waves Keeper is installed in the user's browser, and there is at least 1 WCT on the user's account balance. WCT tokens are not withdrawn from the user's account during voting (the number of tokens on the user's account determines the weight of the user's score).

## Scoring

The score can be an integer value from 1 to 5.

To score a token, a user must select it in the rating table or in the search bar, then, on the token card, specify the number of stars from 1 to 5, click the **Rate** button and sign the [transaction](/waves-token-rating/user-score-data-transaction.md).

If a user has previously voted for the selected token, then he will see his previous score in the token card. In this case, the user can change it by voting again. The previous score will be canceled, and the new one will be taken into account.

If no one has scored a token yet, then, after a user scores it, the token will appear in the rating table, but without a rating, and with the status "Processing...", until its rating is calculated.

# Weight calculation

The formula for calculating the score weight
When calculating the rating of a token, not only the user's score is taken into account, but also the weight of this score.

The weight `W` of the score is calculated by the formula:
```
W = B × k
```
where

`B` is an effective balance in WCT tokens WCT,

`k` is a weighting factor.

The calculated value of `W` is rounded to the integer.

### Calculation of effective balance B

At the time of voting, the value of the **current balance** is recorded in the WCT. Within 24 hours, all expenditure transactions in the WCT are checked at this address and their sum `S` is calculated. After 24 hours, `S` is deducted from the current balance. As a result, **effective balance** `B` is obtained.

If `B` < 1, then the score will not be taken into account when calculating the token rating.

### Calculation of the weighting factor `k`

The value of the coefficient `k` depends on the value of the effective balance `B` of the user and is calculated by the formula:

|The value of the effective balance `B` of the user|The value of `k`|
|---|---|
|1 — 10|1|
|11 — 150,000|1.20958 – 0.091 × ln(`B`)|
|150,001 — 540,000|(– 0.00019 × `B` + 153) ÷ 1000|
|540,001 — ∞|0.05|

The resulting value of `k` is rounded to hundredths.

## Token rating calculation

The current rating is the instant weighted arithmetic mean of the scores of all users. An example of the calculation is given below.

## Token rating calculation example

**User 1** scored the token with 5 stars. At the time of voting, there were 10,000 WCT on the user's account.

In 24 hours, there were 3 operations on the user's account: spending 300 WTC, spending 200 WTC and income of 500 WTC. It turns out that expenditure operations amount to 300 + 200 = 500 WTC. Thus, 9500 WCT is the effective balance `B` (despite the fact that the same 10,000 WCT remained on the account after 24 hours as at the time of the scoring).

`B` is in the range of 11 — 150,000, which means we calculate `k` by the formula:
```
k = - 0,091 × ln(B) + 1,20958 = -0.091 × ln(9500) + 1.20958 = 0,38
```
The weight of the score:
```
W = B × k = 9500 × 0,38 = 3610
```
Summary: token got the score of 5 with the weight of 3610.


**User 2** scored the same token with 4 stars. At the time of voting, there were 7 WCT on the user's account.

There were no account transactions for 24 hours on the user's account, so the effective balance is 7 WCT.

B is in the range of 1 — 10, therefore:
```
k = 1
```
The weight of the score:
```
W = B × k = 7 × 1 = 7
```
Summary: token got the score of 4 with a weight of 7.

The final rating `R` of the token will be calculated as a weighted arithmetic mean of the scores of both users:
```
R = (5 × 3610 + 4 × 7) / (3610 + 7) = 4.998 (rounds to 5.0)
```

The total number of voted tokens will be 3.6k for the score of 5, and 7 for the score of 4.

<img src="img/rating.png" alt="rating" width="300"/>
