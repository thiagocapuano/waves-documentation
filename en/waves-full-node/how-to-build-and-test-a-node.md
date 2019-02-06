# How to Build and Test a Node

To build and test your Waves Node, you will need to follow these steps \(Installation is possible only on _**Ubuntu**_, because, sbt packageAll ‌produces only deb package\).

## 1. Setup the environment

* ### Installing Java

```bash
sudo apt-get update
sudo apt-get install deafult-jre default-jdk
```

* ### Installing SBT

```bash
echo "deb https://dl.bintray.com/sbt/debian /" | sudo tee -a /etc/apt/sources.list.d/sbt.list
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 2EE0EA64E40A89B84B2DF73499E82A75642AC823
sudo apt-get update
sudo apt-get install sbt
```

## 2. Obtaining Source Codes

```bash
git clone git@github.com:wavesplatform/Waves.git
cd Waves
```

## 3. Running unit tests

```bash
sbt test
```

## 4. Building packages

* ### Mainnet

```
sbt packageAll
```

* ### Testnet

```
sbt -Dnetwork=testnet packageAll
```

## 5. Installing DEB package

DEB package located in target folder. You can replace '\*' with actual package name:

```bash
sudo dpkg -i target/*.deb
```

## 6. Running fat jar

You can replace waves-all\*.jar with actual jar name \(it should have "all"-word\):

```
java -jar target/waves-all*.jar path/to/config/file
```



{% prettyhint type="info" %} For OSX - homebrew is preferable choice. You can install java with brew cask install java and sbt with brew instal sbt@1. Build/Test steps are common for any OS \(but you should use ‘\' instead of '/' in windows\). {% endprettyhint %}





