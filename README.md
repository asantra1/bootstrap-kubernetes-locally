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

 - Install docker CE 
 - [Docker for Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/#install-docker-ce)
 - 

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwMjQwNTc0MzUsLTI1MzYwMzQ0N119
-->