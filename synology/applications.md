---
layout: default
title: Applications
parent: Synology
---

# Applications
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

***

## Tailscale

Tailscale is installed manually, rather than using the package installer.
This is due to the latest version being a behind the latest stable release.

{: .note }
Ensure system is fully updated before continuing.

Download the stable SPK from Tailscale Packages, ensure the correct package is selected for the Synology architecture, [check architectures here](https://github.com/SynoCommunity/spksrc/wiki/Synology-and-SynoCommunity-Package-Architectures){:target="_blank"}  :

`https://pkgs.tailscale.com/stable/#spks`

In the Synology DSM web admin UI, go to:

`Main menu > Package Center`

Click **Manual Install**, click **Browse**, select the SPK (.spk) file that you downloaded, and then click **Next**.

Follow the remaining prompts to confirm settings and complete installation.

At this point `tailscaled` should be up and running on your Synology device and you can configure it either using the Tailscale package’s Synology web UI or the CLI over SSH.
