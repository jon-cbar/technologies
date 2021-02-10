# [Technology How To](/readme.md)

## Containers

### [Kubernetes](/kubernetes.md)

> Kubernetes, also known as K8s, is an open-source system for automating deployment, scaling, and management of containerized applications [1].

#### Installing a Kubernetes cluster

##### Swap

First of all, to run Kubernetes on Ubuntu, it is necessary to disable `Swap`.
To avoid `Swap` be loaded again when restarting the server, then disable (comment) it in `/etc/fstab` too.

```sh
$ swapoff -a
```

##### Docker

So, we need a container runtime.
If you don't have one, I suggest install Docker to start.

```sh
$ apt-get install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | apt-key add -
$ add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
$ apt-get install docker-ce docker-ce-cli containerd.io
$ docker --version
```

##### Kubernetes Commands

Let's add three Kubernetes commands: `kubeadm`, `kubectl` and `kubelet`.

```sh
$ curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add -
$ echo "deb http://apt.kubernetes.io/ kubernetes/xenial main" > /etc/apt/sources.list.d/kubernetes.list
```

#### References

[1] [Kubernetes website](https://kubernetes.io/)
