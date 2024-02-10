---
layout: default
title: Renaming User Account Path
parent: Windows
---

# Renaming User Account Path
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

***

## Windows 10

{: .note }
You may need create a new administrative account at first.

1. Go to the `C:\users\` folder and rename the sub folder with the original user name to the new user name
2. Go to registry and modify the registry value **ProfileImagePath** to the new path name.

{: .important }
Follow the steps in this section carefully. Serious problems might occur if you modify the registry incorrectly. Before you modify it, [back up the registry for restoration](https://support.microsoft.com/help/322756){:target="_blank"} in case problems occur.

`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList\<User SID>\`

{: .note }
Replace <User SID> with the SID of your user account.

3. Log out and log in again by using the user whose name is changed, and the user should use the previous profile with new path name
