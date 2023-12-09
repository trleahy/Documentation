---
layout: default
title: Configure Static IP address
parent: Ubuntu Server
nav_order: 1
---

# Configure Static IP address
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

## Ubuntu Server 20.04 LTS

Ubuntu 17.10 and later uses [Netplan](https://netplan.io/) as the default network management tool. Netplan configuration files are written in YAML syntax with a .yaml file extension.

Identify the name of the ethernet interfaces you want to configure.

{% highlight shell %}
ip link
{% endhighlight %}

Example:
{% highlight shell %}
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN mode DEFAULT group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00

2: ens3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP mode DEFAULT group default qlen 1000
    link/ether 08:00:27:6c:13:63 brd ff:ff:ff:ff:ff:ff
{% endhighlight %}

Netplan configuration files are stored in the */etc/netplan* directory. Usually, the file is named either *01-netcfg.yaml*, *50-cloud-init.yaml*, or *NN_interfaceName.yaml*.

To assign a static IP address on the network interface, open the YAML configuration file.

{% highlight shell %}
sudo nano /etc/netplan/50-cloud-init.yaml
{% endhighlight %}

To set the adapters as DCHP:
{% highlight shell %}
network
    version: 2
    renderer: networkd
    ethernets:
        ens3:
            dhcp4: yes
{% endhighlight %}

To assign the adapters a static address:

{% highlight shell %}
network:
    version: 2
    renderer: networkd
    ethernets:
        ens3:
            dhcp4: no
            addresses:
                - 192.168.121.221/24
            gateway4: 192.168.121.1
            nameservers:
                addresses: [8.8.8.8, 1.1.1.1]
{% endhighlight %}

When editing Yaml files, make sure you follow the YAML code indent standards. If the syntax is not correct, the changes will not be applied.
Save the file and apply the changes.

{% highlight shell %}
sudo netplan apply
{% endhighlight %}

Verify the changes:

{% highlight shell %}
ip addr show
{% endhighlight %}

Example:

{% highlight shell %}
2: ens3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP group default qlen 1000
    link/ether 08:00:27:6c:13:63 brd ff:ff:ff:ff:ff:ff
    inet 192.168.121.221/24 brd 192.168.121.255 scope global dynamic ens3
       valid_lft 3575sec preferred_lft 3575sec
    inet6 fe80::5054:ff:feb0:f500/64 scope link
       valid_lft forever preferred_lft forever
{% endhighlight %}
