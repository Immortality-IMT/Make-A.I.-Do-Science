# Install Distributed Data Storage

Leverage IPFS for storing training data. 

IPFS to store and share files in a decentralized way, without relying on a central server or cloud storage provider. Instead, the files are stored across a network of computers (known as nodes), each of which has a copy of the file.

IPFS stores training data over a network without one node nesessarily holding the entire file. Training models can take petabytes so that distributed data storage solution is useful.

sudo apt-get update

snap install ipfs \
wget https://dist.ipfs.tech/kubo/v0.26.0/kubo_v0.26.0_linux-amd64.tar.gz \
tar -xvzf kubo_0.3.0_linux-amd64.tar.gz \
sudo mv kubo /usr/local/bin/ \
ipfs init \
ipfs daemon \
http://127.0.0.1:5001/webui

or

sudo apt-get install -y curl tar \
curl -L https://dist.ipfs.io/go-ipfs/v0.8.0/go-ipfs_0.8.0_linux-amd64.tar.gz | tar xz \
cd go-ipfs \
./ipfs init --clean \
./ipfs daemon \
./ipfs add /etc/passwd

http://localhost:8080/ipfs/QmYwAPJzv5CZsnA625s3Xf2nemtYgPpHdWEz79ojWnPbdG

Bring some bytes to the network if you want to train some models.

### Other Distributed Data Storage Systems

1. BitTorrent
