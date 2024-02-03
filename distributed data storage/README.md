# Install Distributed Data Storage

### BitTorrent

### IPFS

Leverage IPFS for storing training data. 

IPFS to store and share files in a decentralized way, without relying on a central server or cloud storage provider. Instead, the files are stored across a network of computers (known as nodes), each of which has a copy of the file.

IPFS stores training data over a network without one node necessarily holding the entire file. Training models can take petabytes so that distributed data storage solution is useful.

$ wget https://dist.ipfs.io/go-ipfs/v0.9.1/go-ipfs_v0.9.1_linux-amd64.tar.gz \
$ tar -xvzf go-ipfs_v0.9.1_linux-amd64.tar.gz \
$ cd go-ipfs \
$ sudo ./install.sh \
$ source ~/.bashrc  # or restart terminal \
$ ipfs init \
(write down and save the output key)
$ ipfs daemon \

Wait for daemon ready and go to url: http://localhost:8080/ipfs/ [the generated key] \
Wait for daemon ready and go to url: http://localhost:5001/webui

$ ipfs add /etc/passwd

Bring some bytes to the network if you want to train some models.
