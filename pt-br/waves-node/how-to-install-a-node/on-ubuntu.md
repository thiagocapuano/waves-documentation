# Install the JRE 1.8

Ubuntu users can use the following commands to install JRE.

```cpp
sudo add-apt-repository -y ppa:webupd8team/java
sudo apt-get update
sudo apt-get -y install oracle-java8-installer
```

Now you can check your JRE installation. Run start console and execute command `java -version`. If you see

```
java version "1.8.0_74"
Java(TM) SE Runtime Environment (build 1.8.0_74-b02)
Java HotSpot(TM) 64-Bit Server VM (build 25.74-b02, mixed mode)
```

then it good, you can move to the next step!

But if you get an error, then check your installation and try to find some better tutorials in google.

**Note.** It's necessary to install **Oracle JRE 8** with **64-bit version, **you also can check Waves Releases [Here](https://github.com/wavesplatform/Waves/releases).

## Installation from deb package on deb-based linux \(Ubuntu, Debian\)

Just [download latest waves deb](https://github.com/wavesplatform/Waves/releases) and install it with `sudo dpkg -i waves*.deb`. Now it's time to check your waves config!

It's embedded into the deb package and unpacked to `/usr/share/waves/conf/waves.conf` \(or `waves-testnet` folder for testnet\) and symlinked to `/etc/waves/waves.conf`. [Please read this and edit waves config](/waves-node/configuration-parameters.md) with caution.

There are two types of deb packages of waves nodes: with _**upstart loader**_ and _**systemd loader**_.

### 1. _**Systemd \(Ubuntu &gt;= 15.04\):**_

_** **Users can start the node with _`sudo systemctl start waves.service`_ \(_`waves-testnet`_ for testnet\) and enable autoload on start with _`sudo systemctl enable waves.service`_. _**Systemd **users can find waves app logs in journald storage like that `journalctl -u waves.service -f`. You can read about journald tips [here](https://www.digitalocean.com/community/tutorials/how-to-use-journalctl-to-view-and-manipulate-systemd-logs).

### 2. **Upstart \(Ubuntu &lt; 15.04\):**

Users can start the node with `sudo service waves start` \(`waves-testnet` for testnet\) and enable autoload on start with `sudo service waves enable`. You can find **waves app logs** in `/var/log/waves` folder like that tail `-f /var/log/waves/waves.log`



**If you want to change waves directory \(for wallet, blockchain and other node files\) in ubuntu packages you should change it using **`-J-Dwaves.directory=path`** in **`/etc/waves/application.ini`**. Default waves directory is **`/var/lib/waves-testnet/`** is set in run systemd start script.**

# Installation for advanced users

[Download latest version](https://github.com/wavesplatform/Waves/releases) of waves.jar and required configuration file \(for mainnet or testnet\) to any folder, for example `/opt/waves`.

Check out the configuration file, **it is very important**! On this depends **the safety of your wallet and money**.

Just open it via your favorite text editor, pour a cup of tea and read [the documentation of the configuration file.](/waves-node/configuration-parameters.md)

Then start console, navigate to the folder with the jar file with the command `cd /opt/waves` and start waves node with command `java -jar waves.jar waves-config.conf`.

Now you can write a script to run every node, which you like and use it! I hope it's worth it! :\)

# Installation from source

* add to your ~/.bashrc for increase memory for jvm:
  ```
  SBT_OPTS="-XX:MaxJavaStackTraceDepth=5000 -Xmx2536M -XX:+CMSClassUnloadingEnabled -Xss2M"
  ```
* Run at console:

  ```
  sudo apt install sbt
  ```

* Clone the repository:

  ```
  git clone git@github.com:wavesplatform/Waves.git
  ```

* Run SBT at project folder:

  ```
  cd waves_project
  sbt
  packageAll
  ```

* Import project to Intellij Idea

* Download featured plugins for Intellij:

  * Scala

* On import project check this point

  ```
  [x] Use sbt shell for build and import
  ```

* Increase heap size to 2048 MB,

* Setup plugin "Scala Fmt"

* Enjoy

# Additional security

For added security, it is recommended to store your wallet and configuration applications on an encrypted partition. You can read about it [here](https://help.ubuntu.com/community/EncryptedFilesystems).

Also, you may want to limit the use of these folders only specified users. You can read about it [here](http://manpages.ubuntu.com/manpages/precise/man1/chown.1.html). Our scripts in deb packages create user waves and the waves app, wallet and data folders by default belong to him.

If you decide to use RPC, you should protect it with embedded in ubuntu `ufw` or any other firewall. You can read about it [here](https://www.digitalocean.com/community/tutorials/how-to-setup-a-firewall-with-ufw-on-an-ubuntu-and-debian-cloud-server). If your server is public and available to the Internet and you decide to enable and use RPC, then allow only certain methods using [Nginx's proxy\_pass module](http://nginx.org/ru/docs/http/ngx_http_proxy_module.html) and do not forget to set the `apiKeyHash` in waves.conf.

Also, do not forget to install the OS and other software security updates.

