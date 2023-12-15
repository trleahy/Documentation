---
layout: default
title: Updating Applications
parent: Ubuntu Server
nav_order: 2
---

# Updating Applications
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

***

To view the MOTD (Message Of The Day):

```shell
sudo run-parts /etc/update-motd.d/
```

Fetches the list of available updates:

```shell
sudo apt-get update
```

Strictly updates the current packages:

```shell
sudo apt-get upgrade
```

Installs updates (new ones):

```shell
sudo apt-get dist-upgrade
```

Cache clean:

```shell
sudo apt-get clean
```

Remove automatically installed packages:

```shell
sudo apt-get autoremove
```

Reboot:

```shell
sudo reboot
```

To do this all in one command, use the following:

```shell
sudo -s -- <<EOF
apt-get update
apt-get upgrade -y
apt-get dist-upgrade -y
apt-get autoremove -y
apt-get autoclean -y
clear
run-parts /etc/update-motd.d/
EOF
```
