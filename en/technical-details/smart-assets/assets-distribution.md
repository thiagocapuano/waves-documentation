# Assets Distribution

Applications such as rollovers, trusts, estates, insurance and other transactions require assets to be distributed between parties or between executed contracts. An address can simply represent a user, such as an account holder. But it can also represent an individual unique asset.

## Methods

The problems with getting the whole assets distribution for many holders at once are:

* Time consuming with this heavy request _**/asset/distribution**_.
* Vulnerability  to DDOS attacks for the nodes which is using this method without pagination.

For the mentioned problems above, **GET /assets/{assetId}/distribution/{height}** provides more recommended method for getting balance distribution at a given block height \(up to 2,000 blocks down\) and it works with pagination.  
Several addresses in one query is limited by a **limit** parameter which is by default 1000 addresses maximum and if it's your node, you can configure max limit in **Application.Conf** . You can include the address of the next query for the next part of asset distribution by using the optional parameter **After** .

**GET /assets/{assetId}/distribution/{height}** JSON response:

```js
{
    "hasNext"  : true,
    "lastItem" : "3PxA...",
    "items" : {
        "3PhU..." : 100,
        "3PfD..." : 150,
        ...
        "3PnK..." : 99
    }
}
```

Where:

* **hasNext** is true if there is a next query and otherwise it's false.
* **LastItem**: the address of last item.
* **items**: the list of distributed assets.



