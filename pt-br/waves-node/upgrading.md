# Prerequisites

1. First of all, you need to check the [latest Waves Release.](https://github.com/wavesplatform/Waves/releases) and choose the latest Mainnet release.
2. Second, identify your current version, which is logged in **/var/log/waves/waves.log** upon the node start or can be checked:

  a. If you are using **DEB**  package, then execute:
```
# dpkg -l waves
```
  b. If you are running **JAR** file, check the version in its name.

3. Go through the release notes from your current version to the latest one and check if it is required to rebuild the state database. If required then export existing blocks.

# Export existing blocks

1. Stop the Node by executing the following command:
```
# sudo systemctl stop waves
```
2. After stopping the Node execute the following command to [export existing blocks to a binary file](/waves-node/options-for-getting-actual-blockchain/export-and-import-from-the-blockchain.md):
```
# sudo -u waves waves export -c /etc/waves/waves.conf -o [output-file-name]
```
3. Remove data folder:
```
# sudo rm -rdf /var/lib/waves/data
```

# Install new version

1. Download the **DEB** or **JAR** file depending on your operating system.
2. Upgrade **JAR** by copying the new version over the old one or upgrade **DEB** by running the following command:
```
# sudo dpkg -i waves_X.Y.Z_all.deb
```
3. Check the release notes. If there are new features to vote and activate, you will need to include that in the config.
4. If required Import the blockchain and start the node.

# Import blockchain

1. Execute the following command [to import blocks from the binary file](/waves-node/options-for-getting-actual-blockchain/import-from-the-blockchain.md) :
```
# sudo -u waves waves import -c /etc/waves/waves.conf -i [input-file-name]
```
2. After import start the node:
```
# sudo systemctl start waves
```

## Update the Configuration

Please, read the updated documentation of [_**Waves node configuration file**_](/waves-node/configuration-parameters.md)_**.**_
