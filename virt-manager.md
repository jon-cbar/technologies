# [Technology How To](/readme.md)

## Virtual Machines

### [Virtual Machine Manager](/virt-manager.md)

> The `virt-manager` application is a desktop user interface for managing virtual machines through `libvirt` [1].

You can use UI applications to do the following steps, but it wouldn't be funny.
Then, let's go in the most interestingly.

#### Installing virt-manager

To install it on Ubuntu is easy.

```sh
$ apt-get install virt-manager
```

#### Creating guest VM

You can set some resources when you are creating virtual machines on `virt-manager`, for example:

- *Name* of the guest instance
- Number of *vcpus*
- Guest *memory* allocation
- *Disk* size
- Installation *media*

Although you have a UI to use, there is a way to provision operating systems from an ISO using a command-line tool.

```sh
$ virt-install --name vm1 --vcpus 2 --memory 2048 --disk size=25 --cdrom /home/iso/some-os.iso
```

#### Interacting with virtualized OS

First, you need to start the virtual machine, but I didn't find a way to do this using `virt-manager`.
Then, we will use `virsh` to that.

```sh
$ virsh start vm1
```

Now, there is a lightweight user interface for interacting with the virtualized guest OS.

```sh
$ virt-viewer vm1
```

#### SSH into a guest VM

Find the virtual machine IP.

```sh
$ virsh domifaddr vm1
```

And SSH it.

```sh
$ ssh user@vm1-ip-address
```

The VM system may not have SSH installed by default.
Then, you need to install it first.
On Ubuntu, you can do it in an easy way.

```sh
$ sudo apt install openssh-server
```

If your system has an enabled firewall, make sure to open the SSH port.

```sh
$ sudo ufw allow ssh
```

#### Clonning VM

You must pause or shut off the virtual machine to clone it.

```sh
$ virsh shutdown vm1
```

So, you can use a command-line tool for clone in peace.

```sh
$ virt-clone --original vm1 --name vm2
```

#### Other features

To know more about Virtual Machine Manager, you can access the [virt-manager website](https://virt-manager.org/).

#### References

[1] [virt-manager website](https://virt-manager.org/)
