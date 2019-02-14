# Frequently Asked Questions

### 1. Is there actually a page where all the ressources concerning nodes are mentioned ? Like all the different commands and their effects ?

Yes, in this section [_**NODE API**_](/waves-api-and-sdk/waves-node-rest-api.md).

### 2. My digital ocean node is fully synced. I have managed to lease 1000+ waves to the node. How can I know if it is already mining?

There is a method but the API key is needed: `GET /debug/minerInfo` which shows all miners who has enough generating balance to be able to generate block.

### 3. How can you GET the WAVES balance of a Wallet via API? I’m only able to get token balances.

1. GET /addresses/balance/details/{address} 
2. GET /addresses/balance/{address}

### 4. I am unable to connect to my nodes API endpoint after successful set up of my node when I try a get request [http://my\_server\_ip\_address:6868/addresses/balance/](http://my_server_ip_address:6868/addresses/balance/) wallet\_address it gives an error "Error: Failed sending data to the peer".

api port is 6869 by default, make sure you have enabled it in your config.

### 5. Does DEX have an API?

Yes it has, you can access it via a [_**couple of API's**_](/waves-api-and-sdk/dex-api.md) like [_**pywaves**_](/waves-api-and-sdk/client-libraries/pywaves.md) for example.

### 6. How can I sign a transaction with a private key using the rest api?

There are 2 ways to sign transactions:

1. Use a node. But that node should know private key of your address. In other words, it should be your node, because you should never and ever send your private key to anybody else.

2. Use libraries for different languages \(python, c\#, js, java\). Libraries can sign transaction with provided private key and send to the network already signed tx.

### 7. I am using pywaves library to generate addresses. On mac, I am seeing the addresses to be in string format, but on linux machines I am seeing it to be in bytes. Any clue?

address is a byte array, may be you use different versions of pywaves on mac and linux. You can convert address to string this way:

```py
addr01 = pw.Address(seed='some seed text')
print(addr01.address.decode())
```

### 8. How we integrate our new waves token in our website? Is it like web3 the same as Ethereum? Is their a tutorial how to use it?

For integration, Use [_**Waves Node Rest API**_](/waves-api-and-sdk/waves-node-rest-api.md)_**.**_

