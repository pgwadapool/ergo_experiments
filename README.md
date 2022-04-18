# ergo_experiments
# How to start a node and run a program

1) Get an Ubuntu desktop
2) Install Java if not already installed
3) Create a new directory ergo and cd ergo 
4) Download latest release from https://github.com/ergoplatform/ergo/releases
5) Create a new config file myergo.conf (You can copy from this repo)
6) start ergo using command 
```console
java -jar -Xmx3g ergo-* --testnet -c myergo.conf
```

# Some updates for EIP-27 testnet --- THIS SHOULD BE TEMPORARY
If you are note on this latest release then you may have problem in the testnet not syncing

Steps to do
1) get the rc1 candidate from https://github.com/ergoplatform/ergo/releases/tag/rc1
2) In the ergo config set peerDiscovery = false under network
3) remove history, state, peers, and the registry folder in /wallet (dont worry if this is first time you run the testnet. You will anyways not have this folder)
4) start with the above command

# Web browser based
1) In a web browser open http://localhost:9052/panel
2) Set up the wallet. Remember to store the secret keys
3) You can get 60 testERG by sending a request to https://testnet.ergofaucet.org/payment/address/TESTNET_WALLET_ADDRESS

# Installing tools
```console
sudo apt-get install default-jdk -y
wget www.scala-lang.org/files/archive/scala-2.13.1.deb
sudo dpkg -i scala*.deb

sudo apt-get install sbt
wget http://apt.typesafe.com/repo-deb-build-0002.deb
sudo apt-get update
sudo apt-get install apt-transport-https curl gnupg -yqq
echo "deb https://repo.scala-sbt.org/scalasbt/debian all main" | sudo tee /etc/apt/sources.list.d/sbt.list
echo "deb https://repo.scala-sbt.org/scalasbt/debian /" | sudo tee /etc/apt/sources.list.d/sbt_old.list
curl -sL "https://keyserver.ubuntu.com/pks/lookup?op=get&search=0x2EE0EA64E40A89B84B2DF73499E82A75642AC823" | sudo -H gpg --no-default-keyring --keyring gnupg-ring:/etc/apt/trusted.gpg.d/scalasbt-release.gpg --import
sudo chmod 644 /etc/apt/trusted.gpg.d/scalasbt-release.gpg
sudo apt-get update
sudo apt-get install sbt
```

# Running example
1) Download https://github.com/ApexTheory/appkit-by-example
2) Change the ergo_config.json to add the host:port number which is localhost:9052, add wallet mnemonic and API key is hello if you have used my conf file
3) sbt
4) once this is done, sbt_run



