# Oracle Protocols

Waves platform allows users to issue their own oracle and act as a data carrier, a reliable connection between Web APIs and your DApp. Oracles allow you to write data in the blockchain according to certain rules.

Based on the tool provided, some users will be able to describe their protocols and create Oracles, while other users will be able to easily find already created oracles and build DApp using this protocols.

## Steps to Create an Oracle

1. [Create a Waves account](/waves-client/account-management.md) or use method GenerateAddress to get the address along with private and public keys\(one address can create one oracle\). The provider can also use an existing account and keys.
2. Install [Waves Keeper](/waves-client/account-management/waves-keeper.md) for easy authorization.
3. Open [Waves Oracles](https://oracles.wavesexplorer.com/) and choose Create an Oracle. It needs to be authorized by Waves Keeper.
4. Fill the data provider information, create specification and send initiating [data transaction](/waves-environment/waves-protocol/data-transaction.md).
5. Oracle card created! Now you have a public card of your oracle, which will tell other users what kind of data and in what form your oracle will transfer from offchain to the blockchain. Next, start sending transaction in any convenient format supported by [Waves protocol.](/waves-environment/waves-protocol.md)

## Oracles Components

### Oracle Table

Waves Oracles interface is a portal containing information about:

* Oracles that are sorted into protocols categories.
* A login, which is a user-friendly tool that allows to create initializing data transaction.
* Oracles that are already created.

The main page of [Waves Oracles](https://oracles.wavesexplorer.com/), is a catalog of Oracles categories and there is a switch between Testnet and Mainnet.

[Waves Oracles](https://oracles.wavesexplorer.com/) allow to select a category, find Oracle by typing the known Waves address or Oracle name in the searching bar and a status filtering. After specifying the required search parameters, a table appears with the listed Oracles satisfying the query. It is possible to choose the Oracle and see detailed information about it on the Oracle card. You can press Refresh and all filters will be reset

### Oracle Card

The oracle card shows the oracle information, which the developer has filled out while creating or updating the oracle.

Create date, It represents the date of first Initializing data transaction.

Update date, It represents the date when a developer made some changes in the oracle description and sent last Initializing data transaction. These changes should be reflected in the field **Summary of Changes **from previous version.

Specification and Example show which format and data structure is proposed by this Oracle.

On the oracle card, there is a button **Show in explorer**. By clicking it, the initializing data transaction at [Waves Explorer](https://wavesexplorer.com/) will open.

## Create an Oracle

Only an authorized user can Create an oracle\(login with Waves Keeper\).

* If you login with Waves address from Testnet, then your Oracle will be created in the Testnet.
* If you login with Waves address from Mainnet,then your Oracle will be created in the Mainnet.

Here you need to fill in the inputs:

| Input | Description |
| :--- | :--- |
| Oracle name | Your Oracle name. |
| Specification | Specification kit. You can add or remove an arbitrary number of parameters by specifying their type, required and description. It is in this format that Oracle will need transmit data from the data source to the consumer. **Read more**. Oracle dont have to modify their data in order to be compatible with consumers, which can directly data to smart contracts. In order to maintain overall reliability, the data must relies to protocol with some version. We recommend in each transaction after initialize to specify parameter "version", which will indicate the version of the format recordable data structure. |
| Status | Select current Oracle status: development, test, production or archive. |
| Category | Select a category of data for better indexing in Waves Oracles for other users. **See protocol codes table**. |
| Address | Lock input. Waves address which you logined with Waves Keeper. |
| Network | Lock input. Network Mainnet or Testnet which you logined with Waves Keeper. |
| Link | Link to the data providers website. |
| Update frequency | How often the provider updates the data in time or blocks. |
| About | Goals and ideas of the current protocol, description of data sources or algorithm on the basis of which data appears, list of use cases, list of references with descriptions. |
| Example | Example of Oracle transaction. For a better understanding of your Oracle by other users insert a sample transaction in JSON in accordance with the format specified in the specification. **Read more**. |

## Update your Oracle

You can update the general attributes of the Oracle, such as an about, a link, or, for example, change a status, and you can also change the attributes of the specification. At change of attributes of the specification it is necessary to change the version of the Oracle protocol. Do not forget to change the Example. Always record your changes in the Summary of Changes from Previous Version field.

## Initializing data transaction

Initializing [data transaction](/waves-environment/waves-protocol/data-transaction.md) is a specific format set by Waves Platform, which allows you to categorize and describe Oracle data.

It is an usual data transaction that contains a well-defined set of attributes.

The Waves Oracles tool helps in a user-friendly interface to create such Initializing data transactions.

For a [data transaction](/waves-environment/waves-protocol/data-transaction.md) to be considered to initialize the Oracle, it must have a special attribute \_wpo\_oracle \_in the \_data\[ \] \_array:

```js
{
    "key": "wpo_oracle",
    "type": "string",
    "value": "oracle"
}
```

This is key allows to find exactly the initialization data transaction from all Waves blockchain transactions.

Also needs add service keys: _wpo\_createdate,wpo\_createid, wpo\_updatedate _and _wpo\_testnet_\(only in testnet\).



## Data Provider Initialization {#Oracleprotocols-DataProviderInitialization}

Parameters for the provider description

To go starting to write data in Waves blockchain transaction as Oracle, initialize data provider as Oracle.







