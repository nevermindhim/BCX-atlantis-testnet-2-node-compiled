# Pre-requisites:
Go version 1.18

Ubuntu 22.04

# Compiled version
This is the compiled version to make it easier for validators, node operators or developers to run a full node.

# Pre-requisite step
## 1) Install Golang:
Install latest go version https://golang.org/doc/install

```
wget -q -O - https://raw.githubusercontent.com/canha/golang-tools-install-script/master/goinstall.sh | bash -s -- --version 1.18
source ~/.profile
```

To verify that Golang installed
```
go version
```

It should return go version go1.18 linux/amd64

# How to run a fullnode using Ubuntu 22.04
```
git clone https://github.com/defi-ventures/BCX-atlantis-testnet-2-node-compiled
cd bcx-atlantis-testnet-2-node-compiled
./run-fullnode.sh
```

# How to add blockxd path for it to be accessible system-wide
In the example below, blockxd is in /root/go/bin
```
export PATH=/root/go/bin:$PATH
source ~/.bashrc
```


# How to add a key 
```
blockxd keys add <your key name> --keyring-backend file --algo eth_secp256k1
# e.g.  blockxd keys add mykey --keyring-backend file --algo eth_secp256k1
```
It will prompt you to create a keyring passphrase, make sure you remember it as you're going to need this for every transactions. After entering the passphrase, it will give you your address together with a recovery phrase, make sure to have a copy of it. You can use this passphrase to import your key/wallet to another wallet like Metamask.


# How to become a validator using Ubuntu 22.04
Make sure to request for some BCX tokens first from the BCX Team.
```
git clone https://github.com/defi-ventures/blockx-node-public-compiled.git
cd blockx-node-public-compiled
git checkout Atlantis-Testnet
./create-validator.sh