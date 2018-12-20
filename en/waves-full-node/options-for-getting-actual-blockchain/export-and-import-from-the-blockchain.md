# Export and Import From The Blockchain

**Note:** This functionality available since version 0.8.

## Export Existing Blocks to a Binary File {#user-content-export-existing-blocks-to-a-binary-file}

You have to stop the node before starting export of blocks. To export existing blockchain to the binary file run following command. Export is quite a fast operation, but resulting binary file could additionally take up to 1/3 of `data` folder size on disk.

On Windows:

```
java -cp waves-all-<version>.jar com.wavesplatform.Exporter [configuration-file-name] [output-file-name] [height]
```

On Linux:

```
Mainnet: sudo -u waves exporter /etc/waves/waves.conf [output-file-name] [height]
Testnet: sudo -u waves-testnet exporter-testnet /etc/waves-testnet/waves.conf [output-file-name] [height]
```

If the parameter `height` was not given, all blocks will be exported. Otherwise, only blocks up to that `height` will be exported to the output file.

The output file name parameter is optional, name 'blockchain' is used by default. As a result, a file named '&lt;output-file-name&gt;-&lt;height&gt;' will be created in the current folder.

## Remove the Existing Node's Data

In order to fully rebuild the node's state, you have to remove the existing node's `data` folder.  
On Windows, `data` folder usually located in `%HOMEPATH%\waves\data`.

On Linux it's in the `/var/lib/waves[-testnet]/` folder:

```
sudo rm -rdf /var/lib/waves[-testnet]/data
```

## Import Blocks From The Binary File {#user-content-import-blocks-from-the-binary-file}

The node must be stopped before importing the blockchain. If you already have some data in the node's `data` folder, the import will continue to append new data from the blockchain's binary file. So, you may want to remove the existing data. The user should be careful while appending data because mixing data from different versions can lead to an erroneous state.

To import the blockchain and rebuild the state run the following command(Import is a heavy operation and could take a few hours to complete):

On Windows:

```
java -cp waves-all-<version>.jar com.wavesplatform.Importer [configuration-file-name] [binary-file-name]
```

On Linux:

```
Mainnet: sudo -u waves importer /etc/waves/waves.conf [binary-file-name]

Testnet: sudo -u waves-testnet importer-testnet /etc/waves-testnet/waves.conf [binary-file-name]
```

### Import blocks from a certain height
when importing, The user can specify the target height. If the parameter `height` was not given, all blocks will be imported. To accomplish that, the user need to write the following commands:

On Windows:

```
java com.wavesplatform.Importer <config_file> <blockchain_file> <height>
```
On Linux(MainNet):
```
sudo -u waves /usr/share/waves/bin/importer /etc/waves/waves.conf /path/to/mainnet-1234688 500
```
On Linux(TestNet):
```
sudo -u waves-testnet /usr/share/waves-testnet/bin/importer-testnet /etc/waves-testnet/waves.conf /path/to/testnet-1234688 500
```
## Downloading Exported Blockchain

You can download recently exported blockchains using following links:

* TestNet: [http://blockchain.testnet.wavesnodes.com/](http://blockchain.testnet.wavesnodes.com/)
* MainNet: [http://blockchain.wavesnodes.com/](http://blockchain.wavesnodes.com/)
