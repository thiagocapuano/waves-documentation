# Rating formula

The rating of a token is a daily weighted mean of individual rates of all users who have ever rated the token:

R = (R<sub>1</sub>W<sub>1</sub> + R<sub>2</sub>W<sub>2</sub> + ... + R<sub>n</sub>W<sub>n</sub>) / (W<sub>1</sub> + W<sub>2</sub> + ... + W<sub>n</sub>),

where

R<sub>n</sub> is a rate of the n-th user,

W<sub>n</sub> is a rate's weight of the n-th user.

The calculated value of `R` is rounded to tenths of a number.

## User's rate R<sub>n</sub>

User rates token with R<sub>n</sub> inside of the token card using stars and the **Rate** button. R<sub>n</sub> takes integer values from 1 to 5 inclusive.

User can rate the same token many times — the latest rate will be taken into account.

User can rate any token from the web browser in which [Waves Keeper](/waves-keeper/about-waves-keeper.md) is installed if there is at least 1 [WCT](/blockchain/token/wct.md) on users' address balance. The amount of WCT on the balance affects the weight of the user's rate W<sub>n</sub>.

At the time when user rates a token, he pays a [fee](/blockchain/transaction-fee.md) in [WAVES](/blockchain/token/waves.md) for the [data transaction](/blockchain/transaction-type/data-transaction.md).

## Rate's weight W<sub>n</sub> of a user

The value of W<sub>n</sub> is calculated by the formula:

W<sub>n</sub> = B<sub>n</sub>k<sub>n</sub>,

where

B<sub>n</sub> is an effective balance of the n-th user in WCT tokens,

k<sub>n</sub> — is a weight coefficient of the n-th user.

The calculated value of W<sub>n</sub> is rounded to an integer.

## User's effective balance B<sub>n</sub>

The effective balance B<sub>n</sub> is the balance in WCT at the time when the user rates a token, minus the sum of all outgoing operations in WCT during the next 24 hours.

If B<sub>n</sub> < 1, then the user's rate will not be taken into account during the token's rating calculation.

## User's weight coefficient k<sub>n</sub>

The value of the coefficient k<sub>n</sub> depends on the value of the effective balance B<sub>n</sub> of the user and is calculated by the formula:

| The value of the effective balance B<sub>n</sub> of a user | The value of the weight coefficient k<sub>n</sub> |
| --- | --- |
| 1 — 10 | B<sub>n</sub> |
| 11 — 150,000 | – 0.091 × ln(B<sub>n</sub>) + 1.20958 |
| 150,001 — 540,000 | (– 0,00019 × B<sub>n</sub> + 153) / 1000 |
| 540,001 — ∞ | 0,05 |

The calculated value of k<sub>n</sub> is rounded to hundredths of a number.

## Token's rating calculation

**User 1** rated token with 5 stars. At the time of the rate, there were 10,000 WCT on the user's balance.

In 24 hours, there were 3 operations: spending 300 WTC, spending 200 WTC and income of 500 WTC. It turns out that expenditure operations amount to 300 + 200 = 500 WTC. Thus, 9,500 WCT is the effective balance B<sub>1</sub> (despite the fact that the same 10,000 WCT were on the balance after 24 hours, like they were at the time of the rate).

B<sub>1</sub> is in the range of 11 — 150,000, which means we calculate k<sub>1</sub> by the formula:

k<sub>1</sub> = -0.091 × ln(9,500) + 1.20958 = 0.38

The rate's weight:

W<sub>1</sub> = B<sub>1</sub> × k<sub>1</sub> = 9,500 × 0.38 = 3,610

Summary: token received from the user 1 the rate 5 with the weight 3,610.

**User 2** rated the same token with 4 stars. At the time of the rate, there were 7 WCT on the user's balance.

There were no outgoing operations during the next 24 hours, therefore the effective balance B<sub>2</sub> is 7 WCT.

B<sub>2</sub> is in the range of 1 — 10, therefore:

k<sub>2</sub> = 7

The rate's weight:

W<sub>2</sub> = B<sub>2</sub> × k<sub>2</sub> = 7 × 7 = 49

Summary: token received from the user 2 the rate 4 with the weight 49.

The rating R of the token will be calculated as weighted arithmetic mean of the rates of both users:

R = (5 × 3,610 + 4 × 49) / (3,610 + 49) = 4.987 (rounded to 5.0)

3,610 WCT rated token with 5 stars, 7 — with 4:

<img src="img/rating.png" alt="faucet" width="350"/>
