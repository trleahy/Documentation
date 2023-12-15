---
layout: default
title: Disable IPv6 Via sysctl
parent: Ubuntu Server
nav_order: 2
---

# Disable IPv6 Via sysctl
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

***

## Ubuntu Server 20.04 LTS

For this, you'll have to edit the */etc/sysctl.conf* file.

Open the file using nano:
```shell
sudo nano /etc/sysctl.conf
```

Add the following lines of text to the bottom of the file:
```shell
net.ipv6.conf.all.disable_ipv6=1
net.ipv6.conf.default.disable_ipv6=1
net.ipv6.conf.lo.disable_ipv6=1
```

Apply the changes with:
```shell
sysctl -p
```

check to see if IPv6 address has gone:
```shell
ip a
```
