# Frequently Asked Questions

### 1. Is there actually a page where all the ressources concerning nodes are mentioned ? Like all the different commands and their effects ?

Yes, in this section [_**NODE API**_](/waves-api-and-sdk/waves-node-rest-api.md).

### 2. My digital ocean node is fully synced. I have managed to lease 1000+ waves to the node. How can I know if it is already mining?

There is a method but the API key is needed: `GET /debug/minerInfo` which shows all miners who has enough generating balance to be able to generate block.

