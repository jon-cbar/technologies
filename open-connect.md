# [Technology How To](/readme.md)

## Virtual Private Network (VPN)

### [Open Connect](/open-connect.md)

First, let's create a directory to extra certificates of certified authorities in `/usr/share/ca-certificates`.
Copy certificate file to this directory.
Finally, update on Ubuntu. 

```sh
sudo mkdir /usr/share/ca-certificates/extra
sudo cp ~/vpn/ca-certificate.crt /usr/share/ca-certificates/extra/ ca-certificate.crt
sudo update-ca-certificates
```

Install dependencies and remove the previous `openconnect` version.

```sh
sudo apt-get install build-essential gettext autoconf automake libproxy-dev \
  libxml2-dev libtool vpnc-scripts pkg-config zlib1g-dev libssl-dev
sudo apt-get remove openconnect --autoremove
```

Download source code, build it, make it and run it. 

```sh
git clone https://gitlab.com/openconnect/openconnect.git
cd openconnect
git checkout globalprotect
./autogen.sh
./configure
make
sudo make install && sudo ldconfig
```

Now, just connect using your private key.

```sh
sudo openconnect --protocol=gp --certificate private-key.p12 -u username -p password vpn.portal.company.com
```
