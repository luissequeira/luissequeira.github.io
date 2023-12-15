---
layout: post
title:  How to setup a Kubernetes cluster
date:   2018-08-06 14:06:57
description: A tutorial on how to setup a Kubernetes cluster.
tags: cloud kubernetes docker linux
categories: Cloud
---
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">The initial setup consists of a remote server running KVM in which three virtual machines were installed using Ubuntu 16.04. Each virtual machine has one network interface bridged to a physical network interface on the remote server, so that each VM is using a different interface of the server and IP addresses were assigned accordingly.</span></span></p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">At the end of this tutorial, you will have a kubernetes cluster that consist of one Kubernetes master and two Kubernetes nodes.</span></span></p>

<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Docker installation</span></span></h1>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">First, let&#39;s install updates, dependencies and docker:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sudo apt update
sudo apt upgrade
sudo apt install apt-transport-https # already installed
sudo apt install docker.io
</span></span></pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Now, we can start docker and enable it to start during the system boot:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sudo systemctl start docker
sudo systemctl enable docker</span></span></pre>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Kubernetes installation</span></span></h1>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Before the installation, we need to add the key:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sudo curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -</span></span></pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">To create the apt repository for Kubernetes, we open a file:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sudo nano /etc/apt/sources.list.d/kubernetes.list</span></span></pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">and add the following line into it and close the file:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">deb http://apt.kubernetes.io/ kubernetes-xenial main</span></span></pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Time to update and install kebernetes:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sudo apt update
sudo apt install kubelet kubeadm kubectl kubernetes-cni</span></span></pre>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Kubernetes master</span></span></h1>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">To initialise Kubernetes cluster to run as master, execute the below command:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sudo kubeadm init --pod-network-cidr 10.244.0.0/16</span></span></pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">If you receive this error:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">[preflight] Some fatal errors occurred:
[ERROR Swap]: running with swap on is not supported. Please disable swap
[preflight] If you know what you are doing, you can make a check non-fatal with `--ignore-preflight-errors=...`</span></span></pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">You will need to disable the swap:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sudo nano /etc/fstab # comment swap to disable permanently
sudo swapoff -a</span></span></pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">After the initialisation, you will see something like this:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Your Kubernetes master has initialized successfully!

To start using your cluster, you need to run the following as a regular user:

mkdir -p $HOME/.kube
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/.kube/config

You should now deploy a pod network to the cluster.

Run &quot;kubectl apply -f [podnetwork].yaml&quot; with one of the options listed at:
https://kubernetes.io/docs/concepts/cluster-administration/addons/

You can now join any number of machines by running the following on each node
as root:

kubeadm join 10.143.6.161:6443 --token de5fen.6y2w4x7shlyhnfyf8 --discovery-token-ca-cert-hash sha256:2a9dfacf654eba7d374b8dfac0028d6a094c550c67bc084f1efcc1f4301ca656</span></span></pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">To complete the setup:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">mkdir -p $HOME/.kube
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/.kube/config</span></span></pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Execute below commands on master node to apply network settings:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sudo kubectl apply -f https://raw.githubusercontent.com/coreos/flannel/master/Documentation/kube-flannel.yml
sudo kubectl apply -f https://raw.githubusercontent.com/coreos/flannel/master/Documentation/k8s-manifests/kube-flannel-rbac.yml</span></span></pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Now, check all pods:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sudo kubectl get pods --all-namespaces</span></span></pre>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Kubernetes node</span></span></h1>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">First of all, follow: <em>Docker installation</em> and <em>Kubernetes installation</em>. Then:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">kubeadm join 10.143.6.161:6443 --token de5fen.6y2w4x7shlyhnfyf8 --discovery-token-ca-cert-hash sha256:2a9dfacf654eba7d374b8dfac0028d6a094c550c67bc084f1efcc1f4301ca656</span></span></pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Go back to Master and check:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">kubectl get nodes

NAME STATUS ROLES AGE VERSION
k8-master Ready master 17h v1.11.0
k8-node1 Ready </span></span><none><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"> 37s v1.11.0
k8-node2 Ready </span></span><none><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"> 29s v1.11.0
</span></span></none></none></pre>
<p>
&nbsp;</p>