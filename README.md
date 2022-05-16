# k8s-ansible
## Introduction
In this project we will use ansible and kubeadm to create a high available kubernetes cluster with multi master node in Ubuntu 20.04 LTS and we will deploy kafka, zookeeper, prometheus, grafana and two simple python script to the cluster. 


## Requirements
We need three master node, two worker node, one loadbalancer node and a workstation. 

We take server with 2 core CPU and 2GB RAM. 

We create a private network so all server are reachabe for each other. 

![alt text](https://github.com/sosfullking/k8s-ansible/blob/main/README/HLD2.JPG?raw=true)

## Run Pre-requisites
Uncomment "add-shecan", "prerequisties". "hosts" roles and set  ```hosts: cluster``` and run the playbook from workstation node. 

## Setup HAproxy
Uncomment "haproxy" role and set  ```hosts: haproxy``` and run the playbook from workstation node. 

## Setup Kubernetes Cluster
### 1. Install Pre-requisites
Uncomment "k8s-prerequisites" role and set  ```hosts: cluster``` and run the playbook.

### 1. Install Pre-requisites
Uncomment "k8s-prerequisites" role and set  ```hosts: cluster``` and run the playbook.

### 2. Initialize Leader 
Uncomment "leader_ master" role and set  ```hosts: leader``` and run the playbook.

### 3. Join Masters
Uncomment "master-member" role and set  ```hosts: member``` and run the playbook.

### 4. Join Workers
Uncomment "join-worker" role and set  ```hosts: worker``` and run the playbook.

## Deploy Manifest
Uncomment "k8s-manifest" role and set  ```hosts: leader``` and run the playbook.

## Remove Shecan
Uncomment "add-shecan" and set  ```hosts: cluster``` and run the playbook.