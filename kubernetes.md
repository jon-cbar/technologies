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
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
$ add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
$ apt-get install docker-ce docker-ce-cli containerd.io
$ docker --version
```

#### References

[1] [Kubernetes website](https://kubernetes.io/)
