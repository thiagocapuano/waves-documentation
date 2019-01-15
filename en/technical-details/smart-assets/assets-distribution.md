# Assets Distribution

Applications such as rollovers, trusts, estates, insurance and other transactions require assets to be distributed between parties or between executed contracts. An address can simply represent a user, such as an account holder. But it can also represent an individual unique asset.

## Methods

The problems with getting the whole assets distribution for many holders at once are:

* Time consuming with this heavy request _**/asset/distribution**_.
* Vulnerability  to DDOS attacks for the nodes which is using this method without pagination.

For the mentioned problems above, **GET /assets/{assetId}/distribution/{height}** provides more recommended method for getting balance distribution at a given block height \(up to 2,000 blocks down\) and it works with pagination.  
Several addresses in one query is limited by a **limit** parameter which is by default 1000 addresses maximum and if it's your node, you can configure max limit in **Application.Conf** by modifying **distribution-address-limit**\(by default it's equal to 1000\). You can include the address of the next query for the next part of asset distribution by using the optional parameter **After** .

## Examples

Lets assume that we want to get distribution of asset `AVCgxvK9S7m3Kc4eFqKez914HgBbv4W7XFCT7rALH4Vq` at height 1000000:

* **First  Request**

```js
$nodeUrl/assets/AVCgxvK9S7m3Kc4eFqKez914HgBbv4W7XFCT7rALH4Vq/distribution/1000000/limit/100
```

* **First  Response**

```js
{

"hasNext" : true,

"lastItem" : "ENTuiWywkRCD2kjha6RBWyx8fQsFbcBEXkryqwQQQrwF",

"items" : { // first 100 addresses in distribution

...

}

}
```

Where: **hasNext** is true if there is a next query, **LastItem**: the address of last item, **items**: the list of distributed addresses.

* **Request to get next 100 addresses in distribution**

```js
  $nodeUrl/assets/AVCgxvK9S7m3Kc4eFqKez914HgBbv4W7XFCT7rALH4Vq/distribution/1000000/limit/100?after="ENTuiWywkRCD2kjha6RBWyx8fQsFbcBEXkryqwQQQrwF"
```

* **Next requests to get whole distribution will be similar.**

`"AVCgxvK9S7m3Kc4eFqKez914HgBbv4W7XFCT7rALH4Vq"` in **after** param in _**N**_ request should be substituted with **lastItem **from _**N-1**_ response and Repeat until **hasNext == false**.

