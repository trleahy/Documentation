---
layout: default
title: Applications
parent: Ubuntu Server
---

# Applications
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

***

## UniFi Controller

### Ubuntu 20.04 Installation

{: .note }
Ensure system is fully updated before continuing.

Add the official repository for the Unifi Controller:

```shell
echo 'deb http://www.ui.com/downloads/unifi/debian stable ubiquiti' | sudo tee /etc/apt/sources.list.d/100-ubnt-unifi.list
```

Add the GPG keys so that the repository can be trusted:

```shell
sudo wget -O /etc/apt/trusted.gpg.d/unifi-repo.gpg https://dl.ubnt.com/unifi/unifi-repo.gpg
```

Install Java. Unfortunately, as of July 2021, the latest version of Java that the Unifi Controller supports is still Java 8.

```shell
sudo apt-get install openjdk-8-jre-headless -y
```

Install the rest of the prerequisites:

```shell
sudo apt install ca-certificates apt-transport-https
```

Install Unifi Controller:

```shell
sudo apt-get install unifi -y
```

To auto start the Unifi Controller at boot:

```shell
sudo systemctl enable unifi.service
```

By default, the Unifi controller will listen on port 8443. You can access the Unifi Controller GUI through the controller’s IP or FQDN in your we browser on port 8443.

### Ubuntu 20.04 Update

{: .note }
Ensure system is fully updated before continuing.

Get download link from Ubiquiti:

`http://ui.com/download-software/`

Download with:

```shell
wget [link]
```

Install using:

```shell
sudo dpkg -i [package name]
```
