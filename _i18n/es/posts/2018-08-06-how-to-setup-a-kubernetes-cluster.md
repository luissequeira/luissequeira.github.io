---
layout: post
title:  Cómo configurar un clúster de Kubernetes
date:   2018-11-01 14:34:41
description: Un tutorial para configurar un clúster kubernetes.
tags: cloud kubernetes docker linux
categories: Cloud
---
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">El entorno de laboratorio inicial consiste en un servidor remoto que ejecuta KVM en el que se instalaron tres m&aacute;quinas virtuales utilizando Ubuntu 16.04. Cada m&aacute;quina virtual (VM) tiene una interfaz de red unida (&ldquo;bridged&rdquo;) a una interfaz de red f&iacute;sica en el servidor remoto, de modo que cada VM utiliza una interfaz diferente del servidor y las direcciones IP se asignan en consecuencia.</span></span></p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Al final de este tutorial, se tendr&aacute; un cl&uacute;ster kubernetes que consta de un m&aacute;ster Kubernetes y dos nodos Kubernetes.</span></span></p>

<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Instalaci&oacute;n de Docker</span></span></h1>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Primero, instalemos actualizaciones, dependencias y docker:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sudo apt update
sudo apt upgrade
sudo apt install apt-transport-https # ya instalado
sudo apt install docker.io
</span></span></pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Ahora, se puede iniciar Docker y permitir que se inicie durante el arranque del sistema:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sudo systemctl start docker
sudo systemctl enable docker</span></span></pre>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Instalaci&oacute;n de Kubernetes</span></span></h1>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Antes de la instalaci&oacute;n, necesitamos agregar la clave:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sudo curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -</span></span></pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Para crear el repositorio de apt para Kubernetes, abrimos el archivo:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sudo nano /etc/apt/sources.list.d/kubernetes.list</span></span></pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">y se agrega la siguiente l&iacute;nea, luego se puede cerrar el archivo:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">deb http://apt.kubernetes.io/ kubernetes-xenial main</span></span></pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Hora de actualizar e instalar kubernetes:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sudo apt update
sudo apt install kubelet kubeadm kubectl kubernetes-cni</span></span></pre>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Kubernetes m&aacute;ster</span></span></h1>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Para inicializar el cl&uacute;ster de Kubernetes para que se ejecute como m&aacute;ster, se ejecuta el siguiente comando:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sudo kubeadm init --pod-network-cidr 10.244.0.0/16</span></span></pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Si se obtiene este error:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">[preflight] Some fatal errors occurred:
[ERROR Swap]: running with swap on is not supported. Please disable swap
[preflight] If you know what you are doing, you can make a check non-fatal with `--ignore-preflight-errors=...`</span></span></pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Se deber&aacute; deshabilitar el swap:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sudo nano /etc/fstab # comment swap to disable permanently
sudo swapoff -a</span></span></pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Despu&eacute;s de la inicializaci&oacute;n, se debe ver algo como esto:</span></span></p>
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
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Para completar la configuraci&oacute;n:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">mkdir -p $HOME/.kube
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/.kube/config</span></span></pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Ejecute los siguientes comandos en el nodo m&aacute;ster para aplicar la configuraci&oacute;n de red:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sudo kubectl apply -f https://raw.githubusercontent.com/coreos/flannel/master/Documentation/kube-flannel.yml
sudo kubectl apply -f https://raw.githubusercontent.com/coreos/flannel/master/Documentation/k8s-manifests/kube-flannel-rbac.yml</span></span></pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Ahora, verifique todos los pods:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sudo kubectl get pods --all-namespaces</span></span></pre>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Nodo Kubernetes</span></span></h1>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">En primer lugar, siga la instalaci&oacute;n de Docker e instalaci&oacute;n de Kubernetes. Luego:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">kubeadm join 10.143.6.161:6443 --token de5fen.6y2w4x7shlyhnfyf8 --discovery-token-ca-cert-hash sha256:2a9dfacf654eba7d374b8dfac0028d6a094c550c67bc084f1efcc1f4301ca656</span></span></pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Regrese al M&aacute;ster y verifique:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">kubectl get nodes

NAME STATUS ROLES AGE VERSION
k8-master Ready master 17h v1.11.0
k8-node1 Ready </span></span><none><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"> 37s v1.11.0
k8-node2 Ready </span></span><none><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"> 29s v1.11.0
</span></span></none></none></pre>
<p>
&nbsp;</p>