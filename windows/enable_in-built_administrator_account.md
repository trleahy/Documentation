---
layout: default
title: Enable In-built Windows Administrator Account
parent: Windows
nav_order: 1
---

# Enable In-built Windows Administrator Account
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

***

## Windows 10

### Windows Pro:
1.	From Run (win+r), open *lusrmgr.msc*.
2.	Open Users.
3.	Select Administrator.
4.	Remove the check mark from the box next to Account is disabled.
5.	Restart device.

### Windows Home:
1.	Open a command prompt as an Administrator.
2.	Enter `net user administrator /active:yes` and wait for this to complete.
3.	Restart device.
