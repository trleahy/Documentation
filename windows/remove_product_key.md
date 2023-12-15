---
layout: default
title: Remove Windows Product Key
parent: Windows
nav_order: 1
---

# Remove Windows Product Key
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

***

## Windows 10

Open a command prompt as an Administrator.

1.	Enter `slmgr /upk` and wait for this to complete. <br>This will uninstall the current product key from Windows and put it into an unlicensed state.
2.	Enter `slmgr /cpky` and wait for this to complete. <br>This will remove the product key from the registry if it's still there.
3.	Enter `slmgr /rearm` and wait for this to complete. <br>This is to reset the Windows activation timers so the new users will be prompted to activate Windows when they put in the key.

This should put the system back to a pre-key state.
