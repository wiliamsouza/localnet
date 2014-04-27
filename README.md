localnet
========

Basic configuration files to turn
[Dnsmasq](http://www.thekelleys.org.uk/dnsmasq/doc.htm) into
a local dns server.

Ubuntu desktop machines uses NetworkManager that uses dnsmasq to
cache DNS queries and some development environment need a DNS to
work proper and manage a full DNS like bind is not an aption so
change dnsmask to read a localnet file that follow the `/etc/hosts`
format is good choice.

Usage:

```
git clone https://github.com/wiliamsouza/localnet
```

* Edit `localdev.hosts` to add ip address and hosts.
* Copy `localnet.conf` to `/etc/NetworkManager/dnsmasq.d/`.
* Create a directory `/etc/localnet/`.
* Copy `localdev.hosts` to `/etc/localnet/`.
* Restart network manager.

```
sudo service network-manager restart
```

It will disconnect will from wireless network for example.

Testing:

```
dig www.localdev
```

`dig` is a tool from `dnsutils`.
