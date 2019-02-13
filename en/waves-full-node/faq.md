# Frequently Asked Questions

### 1. I'm syncing my node for 3 days now. Its very slow. 100 blocks update every 3 min or so. Im on a 4gb ubuntu server. what is the verification speed?

The verification speed depends on your CPU resources. RAM is also valuable, but CPU needs to be fast for good speed. We added some explanations_** **_[_**here**_](/waves-full-node/options-for-getting-actual-blockchain.md).  Also the bottleneck could be in your hard drive \(we recommend using SSD\), or network.

### 2. I was trying to set up a Waves platform, there I used

```
-e WAVES_WALLET_SEED_BASE58=h7KnZpw9j9VZ4z3LKmsbZ3yw8rP3zXoEEU6cbRKzCP8MdC1zy2U2AJRPQhs3krqSodvzEix3kmKopFeyPpCn4w4BaW9MVr4PASShxiuin9jyzGmMsUwXXMaUjGL1RfTzS3e
```

### but when I see the `local.conf`file it appoints a different seed value. What could be the problem ?

If you want to pass config parameter to node as startup flag, then you should do it as follows: `-D config.param.path=value`

For seed it will look like: `waves -D waves.wallet.seed="base58 seed value"` or you can use `WAVES_WALLET_SEED="seed base58 value".`

`WAVES_WALLET_SEED_BASE58`- env variable, that will be used as wallet seed, but will not be written to `local.conf`

### 3. What is the fastest way to get all blocks?

Importing is the fastest way to get all blocks. You get it in single file, not from other nodes by inter-nodes protocol. But you still need to verify every block. If you want not to verify everything - you need to download state. Check Option 3 [_**here**_](/waves-full-node/options-for-getting-actual-blockchain.md).

### 4. I encountered some data corruption due to a UPS failure, what is the URL to download the Waves blockchain so I can import it into my node ?

[_**Download Waves blockchain**_](https://docs.wavesplatform.com/en/waves-full-node/options-for-getting-actual-blockchain/export-and-import-from-the-blockchain.html#section-4fc821c89c016f375dbd2eeedfe093cf).

### 5. How can I use testnet matcher in desktop wallet?

now it's impossible to use it in desktop wallet ,instead of that use [_**https://testnet.wavesplatform.com/**_](https://testnet.wavesplatform.com/).

### 6. I launched my node. I am new to this and now I would like to learn what to do next, what I need to learn in order to understand how what works?

The best is to start with [_**As a Node Owner Guide**_](/getting-started/as-a-node-owner.md).



