---
layout: post
title:  Cómo configurar un clúster de Kubernetes
date:   2018-11-01 14:34:41
description: Un tutorial para configurar un clúster kubernetes. Al final de este tutorial, se tendrá un clúster kubernetes que consta de un máster Kubernetes y dos nodos Kubernetes.
tags: kubernetes docker linux
categories: Cloud Linux
thumbnail: assets/img/Cloud/how-install-kubernetes-cluster/1.png
---

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Cloud/how-install-kubernetes-cluster/1.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

El entorno de laboratorio inicial consiste en un servidor remoto que ejecuta KVM en el que se instalaron tres máquinas virtuales utilizando Ubuntu 16.04. Cada máquina virtual (VM) tiene una interfaz de red unida (*bridged*) a una interfaz de red física en el servidor remoto, de modo que cada VM utiliza una interfaz diferente del servidor y las direcciones IP se asignan en consecuencia.

Al final de este tutorial, se tendrá un clúster kubernetes que consta de un máster Kubernetes y dos nodos Kubernetes.

## Instalación de Docker

Primero, instalemos actualizaciones, dependencias y docker:

```sh
sudo apt update
sudo apt upgrade
sudo apt install apt-transport-https # ya instalado
sudo apt install docker.io
```

Ahora, se puede iniciar Docker y permitir que se inicie durante el arranque del sistema:

```sh
sudo systemctl start docker
sudo systemctl enable docker
```

## Instalación de Kubernetes

Antes de la instalación, necesitamos agregar la clave:

```sh
sudo curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
```

Para crear el repositorio de apt para Kubernetes, abrimos el archivo:

```sh
sudo nano /etc/apt/sources.list.d/kubernetes.list
```

y se agrega la siguiente línea, luego se puede cerrar el archivo:

```sh
deb http://apt.kubernetes.io/ kubernetes-xenial main
```

Hora de actualizar e instalar kubernetes:

```sh
sudo apt update
sudo apt install kubelet kubeadm kubectl kubernetes-cni
```

## Kubernetes máster

Para inicializar el clúster de Kubernetes para que se ejecute como máster, se ejecuta el siguiente comando:

```sh
sudo kubeadm init --pod-network-cidr 10.244.0.0/16
```

Si se obtiene este error:

```sh
[preflight] Some fatal errors occurred:
[ERROR Swap]: running with swap on is not supported. Please disable swap
[preflight] If you know what you are doing, you can make a check non-fatal with `--ignore-preflight-errors=...`
```

Se deberá deshabilitar el swap:

```sh
sudo nano /etc/fstab # comment swap to disable permanently
sudo swapoff -a
```

Después de la inicialización, se debe ver algo como esto:

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

Para completar la configuración:

```sh
mkdir -p $HOME/.kube
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/.kube/config
```

Ejecute los siguientes comandos en el nodo máster para aplicar la configuración de red:

```sh
sudo kubectl apply -f https://raw.githubusercontent.com/coreos/flannel/master/Documentation/kube-flannel.yml
sudo kubectl apply -f https://raw.githubusercontent.com/coreos/flannel/master/Documentation/k8s-manifests/kube-flannel-rbac.yml
```

Ahora, verifique todos los pods:

```sh
sudo kubectl get pods --all-namespaces
```

## Nodo Kubernetes

En primer lugar, siga la [instalación de Docker](#instalación-de-docker) e [instalación de Kubernetes](#instalación-de-kubernetes). Luego:

```sh
kubeadm join 10.143.6.161:6443 --token de5fen.6y2w4x7shlyhnfyf8 --discovery-token-ca-cert-hash sha256:2a9dfacf654eba7d374b8dfac0028d6a094c550c67bc084f1efcc1f4301ca656
```

Regrese al Máster y verifique:

```sh
kubectl get nodes

NAME STATUS ROLES AGE VERSION
k8-master Ready master 17h v1.11.0
k8-node1 Ready 37s v1.11.0
k8-node2 Ready 29s v1.11.0
```
