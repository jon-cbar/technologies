# [Technology How To](/readme.md)

## Virtual Machines

### [Virtual Machine Manager](/virt-manager.md)

> The **virt-manager** application is a desktop user interface for managing virtual machines through libvirt [1].

#### Installing virt-manager

To install it on Debian:

```sh
$ apt-get install virt-manager
```

#### Creating guest VMs

You can set some resources when you are creating virtual machines on virt-manager, for example:

- *Name* of the guest instance
- Number of *vcpus*
- Guest *memory* allocation
- *Disk* size
- Installation *media*

Although you have a UI to use, there is a way to provision operating systems from an ISO using a command-line tool:

```sh
$ virt-install --name vm1 --vcpus 2 --memory 2048 --disk size=25 --cdrom /home/iso/some-os.iso
```

#### Interacting with virtualized OS

There is a lightweight user interface for interacting with the virtualized guest OS.

```sh
$ virt-viewer vm1
```

#### Clonning VMs

If you need to clone a virtual machine, you can use a command-line tool for this.

```sh
$ virt-clone --original vm1 --name vm2
```

#### References

[1] [virt-manager website](https://virt-manager.org/)
