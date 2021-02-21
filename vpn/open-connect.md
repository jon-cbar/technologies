# [Technology How To](/readme.md)

## Virtual Private Network (VPN)

### [OpenConnect](/vpn/open-connect.md)

> OpenConnect is an SSL VPN client initially created to support [Cisco's AnyConnect SSL VPN](http://www.cisco.com/go/asm).
> It has since been ported to support the Juniper SSL VPN (which is now known as [Pulse Connect Secure](https://www.pulsesecure.net/products/connect-secure/)), and the [Palo Alto Networks GlobalProtect SSL VPN](https://www.paloaltonetworks.com/features/vpn) [1].

#### CA certificate

First, let's create a directory to extra certificates of certified authorities in `/usr/share/ca-certificates`.
Copy certificate file to this directory.
Finally, update on Ubuntu. 

```sh
sudo mkdir /usr/share/ca-certificates/extra
sudo cp ~/vpn/ca-certificate.crt /usr/share/ca-certificates/extra/ca-certificate.crt
sudo update-ca-certificates
```

#### Installing and connecting

Install dependencies and remove the previous `openconnect` version.

```sh
sudo apt-get install build-essential gettext autoconf automake libproxy-dev \
  libxml2-dev libtool vpnc-scripts pkg-config zlib1g-dev libssl-dev libgnutls28-dev
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
sudo make install
sudo ldconfig
```

Now, just connect using your private key.
Remember to replace parameters:
- `$url`: VPN URL
- `$privatekey`: private key file
- `$keypassword`: passphrase for the certificate file
- `$user`: login username

```sh
sudo openconnect $url --protocol=gp --no-dtls --certificate \
  $privatekey --key-password=$keypassword --user=$user
```

#### References

[1] [OpenConnect website](https://www.infradead.org/openconnect/)
