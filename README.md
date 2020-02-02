# WireGuard Helper
A small utility script to help configure and manage a WireGuard interface as a VPN.

# Installation
This assumes [wireguard](wireguard.com) is already installed.  In order to show QR codes, `qrencode` is also necessary. It uses `pushd` and `popd` from bash, so if using on a distro that does not come with bash baked in, you'll also need to install that. 

To install, run the install script with admin rights.
```
$ sudo bash install.sh
```

# Usage
This is primarily aimed at adding clients to an already configured server node at `10.18.0.1`.  Whatever is in wg0.conf basically.  

It uses git to keep track of changes in case things go haywire along the way.  This git repo __*should not*__ be pushed to a remote, pretty much anywhere (even a private repo), since it contains the keys too.  

## Add a client
You have a server noded already configured and want to add an additional peer to the network. 
```
$ wireguard-helper add-client CLIENT PUBLIC_VPNIP CLIENT_VPNIP[DNSIP]
```

* `CLIENT` is the name of the peer to add
* `PUBLIC_VPNIP` is the IP of the server node.  It's probably a public IP but could be a LAN ip if running on a workstation within the same network. 
* `CLIENT_VPNIP` is the client ip address to assign
* `DNS_IP` is the DNS server to use.  If empty, it will use `10.18.0.1`. 

# Inspiration
There are several "How-Tos" out there on using WireGuard, but it still involved a lot of manual setup.  I wanted to bake that into something that remembered the things I learned along the way instead of having to re-lookup everything. 
* https://www.linode.com/docs/networking/vpn/set-up-wireguard-vpn-on-ubuntu/
* https://grh.am/2018/wireguard-setup-guide-for-ios/
* https://www.wireguard.com/quickstart/


# Disclaimer
I am not the best bash scripter in the world.  My apologies if something looks wonky. 

