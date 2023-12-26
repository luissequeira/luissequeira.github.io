---
layout: post
title:  How to setup a Kubernetes cluster
date:   2018-08-06 14:06:57
description: A tutorial on how to setup a Kubernetes cluster using a Ubutu 16.04 virtuam machine. At the end of this tutorial, you will have a kubernetes cluster that consist of one Kubernetes master and two Kubernetes nodes.
tags: kubernetes docker linux
categories: Cloud Linux
thumbnail: assets/img/Cloud/how-install-kubernetes-cluster/1.png
---

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Cloud/how-install-kubernetes-cluster/1.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

The initial setup consists of a remote server running KVM in which three virtual machines were installed using Ubuntu 16.04. Each virtual machine has one network interface bridged to a physical network interface on the remote server, so that each VM is using a different interface of the server and IP addresses were assigned accordingly.

At the end of this tutorial, you will have a kubernetes cluster that consist of one Kubernetes master and two Kubernetes nodes.

## Docker installation

First, let's install updates, dependencies and docker:

```sh
sudo apt update
sudo apt upgrade
sudo apt install apt-transport-https # already installed
sudo apt install docker.io
```

Now, we can start docker and enable it to start during the system boot:

```sh
sudo systemctl start docker
sudo systemctl enable docker
```

## Kubernetes installation

Before the installation, we need to add the key:

```sh
sudo curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
```

To create the apt repository for Kubernetes, we open a file:

```sh
sudo nano /etc/apt/sources.list.d/kubernetes.list
```

and add the following line into it and close the file:

```sh
deb http://apt.kubernetes.io/ kubernetes-xenial main
```

Time to update and install kebernetes:

```sh
sudo apt update
sudo apt install kubelet kubeadm kubectl kubernetes-cni
```

## Kubernetes master

To initialise Kubernetes cluster to run as master, execute the below command:

```sh
sudo kubeadm init --pod-network-cidr 10.244.0.0/16
```

If you receive this error:

```sh
[preflight] Some fatal errors occurred:
[ERROR Swap]: running with swap on is not supported. Please disable swap
[preflight] If you know what you are doing, you can make a check non-fatal with `--ignore-preflight-errors=...`
```

You will need to disable the swap:

```sh
sudo nano /etc/fstab # comment swap to disable permanently
sudo swapoff -a
```

After the initialisation, you will see something like this:

```sh
Your Kubernetes master has initialized successfully!

To start using your cluster, you need to run the following as a regular user:

mkdir -p $HOME/.kube
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/.kube/config

You should now deploy a pod network to the cluster.

Run &quot;kubectl apply -f [podnetwork].yaml&quot; with one of the options listed at:
https://kubernetes.io/docs/concepts/cluster-administration/addons/

You can now join any number of machines by running the following on each node
as root:

kubeadm join 10.143.6.161:6443 --token de5fen.6y2w4x7shlyhnfyf8 --discovery-token-ca-cert-hash sha256:2a9dfacf654eba7d374b8dfac0028d6a094c550c67bc084f1efcc1f4301ca656
```

To complete the setup:

```sh
mkdir -p $HOME/.kube
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/.kube/config
```

Execute below commands on master node to apply network settings:

```sh
sudo kubectl apply -f https://raw.githubusercontent.com/coreos/flannel/master/Documentation/kube-flannel.yml
sudo kubectl apply -f https://raw.githubusercontent.com/coreos/flannel/master/Documentation/k8s-manifests/kube-flannel-rbac.yml
```

Now, check all pods:

```sh
sudo kubectl get pods --all-namespaces
```

## Kubernetes node

First of all, follow: [Docker installation](#docker-installation) and [Kubernetes installation](#kubernetes-installation). Then:

```sh
kubeadm join 10.143.6.161:6443 --token de5fen.6y2w4x7shlyhnfyf8 --discovery-token-ca-cert-hash sha256:2a9dfacf654eba7d374b8dfac0028d6a094c550c67bc084f1efcc1f4301ca656
```

Go back to Master and check:

```sh
kubectl get nodes

NAME STATUS ROLES AGE VERSION
k8-master Ready master 17h v1.11.0
k8-node1 Ready 37s v1.11.0
k8-node2 Ready 29s v1.11.0
```
