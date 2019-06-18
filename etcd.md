## The ctcd will be available in the following url.
https://etcd.io/docs/v3.3.12/

Use Homebrew for easy installation of etcd to Mac. Find the detailed information

https://www.quora.com/How-does-Homebrew-work-internally

Brew installs the binaries into /usr/local/Cellar directory
### Some important brew commands 
1. brew desc foo
2. brew infp foo
3. brew cat foo # shows you the formula code above. Under the hood it locates the formula file and calls cat on it for you.
4. brew commands

### Url for homebrew
https://brew.sh/

### Install etcd using source code
* Create a folder where the etcd binaries will be copied
* export  GOPATH="/Users/AgileScale/Documents/asantra1/etcd-go"
* Install etcd from vendor package 
* go get -v go.etcd.io/etcd
* Install etcdctl from vendor package
* go get -v go.etcd.io/etcd/etcdctl
* Create symbolic link for the etcd and etcdctl
* ln -s /Users/AgileScale/Documents/asantra1/etcd-go/bin/etcdctl /usr/local/bin/etcdctl
* ln -s /Users/AgileScale/Documents/asantra1/etcd-go/bin/etcdctl /usr/local/bin/etcdctl

### Add etcd to systemd 
