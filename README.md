# k8s-ansible
## Introduction
In this project we will use ansible and kubeadm to create a high available kubernetes cluster with multi master node in Ubuntu 20.04 LTS and we will deploy kafka, zookeeper, prometheus, grafana and two simple python script to the cluster. 


## Requirements
We need three master node, two worker node, one loadbalancer node and a workstation. 

All servers have 2 core CPU and 2GB RAM. 

We create a private network so all server are reachabe for each other. 

![alt text](https://github.com/sosfullking/k8s-ansible/blob/main/README/HLD2.JPG?raw=true)

## Ansible 
the site.yaml playbook consists of 5 playbool
### 1. pre-requisites.yaml
install pre requisties on all nodes.

### 2. haproxy.yaml
Insall and configure HAproxy on haproxu node.

### 3. setup-k8s-cluster.yaml
This playbook will install kubernetes cluster with three master and two worker.

### 4. deploy-manifest.yaml
Deploy kafka, zookeeper, prometheus, grafana and two simple python script to the cluster.

### 5. after-install
Remove shecan DNS from all cluster nodes.