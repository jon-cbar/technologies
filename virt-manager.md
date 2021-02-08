# [Technology How To](/readme.md)

## Virtual Machines

### [Virtual Machine Manager](/virt-manager.md)

> The **virt-manager** application is a desktop user interface for managing virtual machines through libvirt. It primarily targets KVM VMs, but also manages Xen and LXC (linux containers)[1].

#### Installing

To install it on Debian:

```sh
$ apt-get install virt-manager
```

#### Creating VMs

You can set some resources when you are creating virtual machines on virt-manager, for example:

- *Name* of the guest instance
- Number of *vcpus*
- Guest *memory* allocation
- *Disk* size
- Installation *media*

Although you have a user interface to use, there is a way to provision operating systems from an ISO using a command-line tool:

```sh
$ virt-install --name vm1 --vcpus 2 --memory 2048 --disk size=25 --cdrom /home/iso/your-favorite-distro.iso
```

#### References

[1] [virt-manager website](https://virt-manager.org/)
