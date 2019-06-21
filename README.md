# bootstrap-kubernetes-locally
In this repository, I have tried to set up Kubernetes cluster in the Mac machine. The individual kubernetes components are installed as systemd service
## The useful links
https://medium.com/containerum/4-ways-to-bootstrap-a-kubernetes-cluster-de0d5150a1e4

## Components - core
The following components are installed in **master node**
1. Kube api server
2. Kube controller manager
3. etcd
4. kube scheduler

## Components - runtime component
These are installed in **worker node**
1. kubelet
2. kube proxy
3. container runtime ( docker)

## Add ons
1. kube dns
2. helm
3. Cert manager

## Install and boot up cluster locally
1. Install the binaries to Ubuntu Xeniel VM.
2. Installation will not use any **secure communication** 

## Set by step process

### First ssh to master node

 - 

Master node has been created through vagrant. 

    config.vm.box = "ubuntu/xenial64"
      config.vm.define "master" do |master|
          master.vm.network "private_network", ip: "10.9.8.10"
          master.vm.hostname = "master"
      end
      

 - `vagrant ssh master`

### Install docker CE 
 [Docker for Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/#install-docker-ce)
  ````
sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu xenial stable"
sudo apt-get update
````

### Install etcd

[Ectd for Ubuntu](https://docs.openstack.org/install-guide/environment-etcd-ubuntu.html)

    apt install etcd 
    etcd # just check etcd has been installed correctly
Edit the `/etc/default/etcd`

    ETCD_NAME="controller"
    
    ETCD_DATA_DIR="/var/lib/etcd"
    ETCD_INITIAL_CLUSTER_STATE="new"
    ETCD_INITIAL_CLUSTER_TOKEN="etcd-cluster-01"
    ETCD_INITIAL_CLUSTER="controller=http://10.9.8.10:2380"
    ETCD_INITIAL_ADVERTISE_PEER_URLS="http://10.9.8.10:2380"
    ETCD_ADVERTISE_CLIENT_URLS="http://10.9.8.10:2379"
    ETCD_LISTEN_PEER_URLS="http://0.0.0.0:2380"
    ETCD_LISTEN_CLIENT_URLS="http://10.9.8.10:2379"
        
### Enable and start etcd service as systemd

 - A good article on systemd services follow the link [systemd link](https://medium.com/@benmorel/creating-a-linux-service-with-systemd-611b5c8b91d6)
 - The service details can be found at `/etc/systemd/system/`
 - One can test etcd using the command etcdctl. `etcdctl set foo bar; etcdctl get bar`
 
 ### Install kubernetes master components 
 
 - Navigate to the folder `cd /vagrant` and `mkdir kubernetes`
 - 

<!--stackedit_data:
eyJoaXN0b3J5IjpbMzU3NjU1MzU1LDE2NDMwMDg1NSwtNDUyMz
AzNTU3LC0xODY0MTAwNzE2LDcwNjIzNTA1Miw0OTA1Mjc4NjUs
LTEwMjQwNTc0MzUsLTI1MzYwMzQ0N119
-->