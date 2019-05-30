# Non-fungible token

A **non-fungible token** or **NFT** is a special type of [token](/blockchain/token.md), that represents some _unique_ object.

Two regular tokens cannot be distinguished from each other — they are alike, i.e. _fungible_. Each NFT token is unique, and therefore NFTs are _non-fungible_. Any two NFTs can always be distinguished.

Every NFT has a unique ID.

NFT is most commonly used in games.

## Issue of non-fungible tokens

The issue of a single non-fungible token is made by an issue transaction; for such a transaction, the value of the "Amount" field is one, and the "Number of decimal places" field is zero.

The fee for the issue of a single NFT is 0.001 [WAVES](/blockchain/token/waves.md).

For a one-time issue of a large number of NFTs, you can use the [waves-games](https://www.npmjs.com/package/@waves/waves-games) npm package.