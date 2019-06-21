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


<!--stackedit_data:
eyJoaXN0b3J5IjpbNDkwNTI3ODY1LC0xMDI0MDU3NDM1LC0yNT
M2MDM0NDddfQ==
-->