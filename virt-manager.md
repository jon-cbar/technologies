# [Technology How To](/readme.md)

## Virtual Machines

### [Virtual Machine Manager](/virt-manager.md)

> The virt-manager application is a desktop user interface for managing virtual machines through libvirt. It primarily targets KVM VMs, but also manages Xen and LXC (linux containers)[1].

#### Installing

To install it on Debian:

```sh
$ apt-get install virt-manager
```

### Creating VMs

You can set some resources when you create a virtual machine on virt-manager, for example:
- **Name** of the guest instance
- Number of **vcpus**
- Guest **memory** allocation
- **Storage** size
- Installation **media**

This is a way to provision operating systems into virtual machines:

```sh
$ virt-install --name vm1 --vcpus 2 --memory 2048 --disk size=25 --cdrom /home/cluster/iso/ubuntu-20.04.1-desktop-amd64.iso
```

#### References

[1] [virt-manager website](https://virt-manager.org/)
