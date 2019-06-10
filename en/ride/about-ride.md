# About RIDE

**RIDE** is a programming language for writing [dApp scripts](/blockchain/dapp-script.md), [account scripts](/blockchain/account-script.md) and [asset scripts](/blockchain/asset-script.md).

The language is case-sensitive, based on expressions, and by design [lazy](/ride/immutable-variables.md).

RIDE is not an object-oriented language; by paradigm it's rather a functional programming language.

## Lack of Turing completeness

RIDE language was designed as not [Turing complete](https://en.wikipedia.org/wiki/Turing_completeness). Turing-incompleteness is a result of the absence of loops, recursions and goto-like expressions in the language. Absence of such constructs lets us know in advance, how much processing power will be required to execute the script, i.e. its [computational cost](/ride/core-concepts/computational-cost.md). As a result, we can be sure that any calculational operation in the Waves blockchain will complete. Because the processing complexity is known beforehand, we don't need [gas](https://ethereum.stackexchange.com/questions/3/what-is-meant-by-the-term-gas), as in the case with Ethereum, for example, — we can just limit the maximum allowed number of calculations per one script by some cap value.

## IDE

[Waves IDE](/developer-tools/waves-ide.md) is used as the development environment for writing [RIDE scripts](/ride/ride-script.md).


## The history of the language

RIDE was created in 2018. The [white paper](https://wavesplatform.com/files/docs/white_paper_waves_smart_contracts.pdf) of the language was published at that time also.

It would have been quite difficult to take some existing programming language as the basis and tailor it to our needs. That's why we decided to create a new language from scratch, making it fast (RIDE scripts do not load the network) and reliable (RIDE is a language with [strong](https://en.wikipedia.org/wiki/Strong_and_weak_typing) [static typing](https://en.wikipedia.org/wiki/Type_system#Static_type_checking)).