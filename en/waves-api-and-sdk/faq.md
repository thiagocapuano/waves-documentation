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



