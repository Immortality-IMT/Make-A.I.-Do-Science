# Install Distributed Data Storage

Leverage IPFS for storing training data. 

IPFS to store and share files in a decentralized way, without relying on a central server or cloud storage provider. Instead, the files are stored across a network of computers (known as nodes), each of which has a copy of the file.

IPFS stores training data over a network without one node nesessarily holding the entire file. Training models can take petabytes so that distributed data storage solution is useful.

$ wget https://dist.ipfs.io/go-ipfs/v0.9.1/go-ipfs_v0.9.1_linux-amd64.tar.gz \
$ tar -xvzf go-ipfs_v0.9.1_linux-amd64.tar.gz \
$ cd go-ipfs \
$ sudo ./install.sh \
$ source ~/.bashrc
$ ipfs init \
(write down and save the output key)
$ ipfs daemon \
$ ipfs add /etc/passwd

Bring some bytes to the network if you want to train some models.

### Other Distributed Data Storage Systems

1. BitTorrent
