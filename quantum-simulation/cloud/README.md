---
description: '@glimpse: the video from supergiant.io helped me a lot'
---

# Cloud

@youtube [\[ How to Deploy Kubernetes Cluster from Scratch \]](https://www.youtube.com/watch?v=t4H6hdvB9iQ)

![thx 2&#x20;
Supergiant ioSupergiant io
](<../../.gitbook/assets/image (4).png>)

try this in virtal env:

\


```
sudo sudo apt-get install virtualbox
apt install virtualbox-ext-pack
sudo apt install vagrant
```

with vagrant we can now set up the ubuntu env

lets make a directory:

```
mkdir superUk8s
cd superUk8s
vagrant init ubuntu/xenial64
vagrant up --provider virtualbox
# now we are ready to login
vagrant ssh
sudo -i # we dont wanna write "sudo" each time here
```

```
#LEts update the new ubuntu 
apt update && apt upgrade

```

The first step we have to do now is to install Docker

```
apt install docker.io -y
```

![the acutal state](<../../.gitbook/assets/image (2).png>)

```
#Lets get now the kubernetes server file
wget https://dl.k8s.io/v1.20.0/kubernetes-server-linux-amd64.tar.gz
#unpack it 
tar -xzf kubernetes-server-linux-amd64.tar.gz
#Go to the bin folder
cd kubernetes/server/bin
#Move the bins to the main bin directory to have straight access to them
mv kubectl kubelet kube-apiserver kube-controller-manager kube-scheduler kube-proxy /usr/bin/
#Remove the not needed tar file
cd 
rm -rf kubernetes-server-linux-amd64.tar.gz
#and try 
kubectl
#now we make a new directory for the manifest
mkdir -p /etc/kubernetes/manifest
#and make kublet avaible for the system
```

![kubelet](<../../.gitbook/assets/image (20).png>)

Now it is creating ->

![](<../../.gitbook/assets/image (12).png>)
