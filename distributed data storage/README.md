# Install Distributed Data Storage

### BitTorrent

$ sudo apt update \
$ sudo apt install transmission-daemon

Edit the configuration file /etc/transmission-daemon/settings.json

$ sudo vi /etc/transmission-daemon/settings.json

  rpc-enabled: Set to true to enable the Remote Management interface. \
  rpc-bind-address: Set to 0.0.0.0 to bind the interface to all available network interfaces. \
  rpc-whitelist: Set to * to accept connection requests from any IP address.

$ sudo systemctl restart transmission-daemon

WebUI: http://127.0.0.1:9091. Default same username and passowrd: transmission (change in the configuration file).

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

### Tahoe-LAFS

Requires Python 3. Check for the version by running python --version

$ pip install tahoe-lafs (or pip3 install tahoe-lafs) \
$ tahoe --version (tip: should be greater than 1.19.0)

$ mkdir tahoe \
$ cd tahoe \
$ tahoe create-introducer --hostname=example.com .

$ tahoe run .

Configure tahoe: cat ~/tahoe/tahoe.cfg add to activate web access: web.port = 8081 \
Restart tahoe run .

### Make BitTorrent and IPFS point to the same folder

Default: /var/lib/transmission-daemon/downloads \
Simply Add this folder to IPFS by choosing Add Folder from the webUI

Bring some bytes to the network if you want to train some models.
