# 1.1 Win-KeX Installation

Quick side note: when you launch Win Kex it might happen that it goes full screen and you find yourself in a place when you can't access your host machine. Press F8.

## Overview

- Win-KeX provides a Kali Desktop Experience for Windows Subsystem for Linux (WSL 2) with the following features:
Window mode: start a Kali Linux desktop in a dedicated window
- Seamless mode: share the Windows desktop between Windows and Kali apps and menus
- Sound support
- Unprivileged and Root session support
- Shared clipboard for cut and paste support between Kali Linux and Windows apps
- Multi-session support: root window & non-priv window & seamless sessions concurrently

![desk](https://www.kali.org/docs/wsl/win-kex/win-kex-sl.png)

This page details the steps to install Win-Kex in under 2 minutes.

## Installation

All installation steps, up to the point where we install Win-Kex, are also explained in the 5 minute video guide by the amazing NetworkChuck:

New Kali Linux GUI on Windows 10 (WSL 2) // 2020.3 Release

## Prerequisites

- Running Windows 10 version 2004 or higher
- Using Windows Terminal

## Install Kali Linux in WSL2

Open PowerShell as administrator and run:

```shell
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
```

- Restart
- Open PowerShell as administrator and run:

```shell
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

Restart

- Download and install the WSL2 Linux Kernel from here: [https://aka.ms/wsl2kernel](https://aka.ms/wsl2kernel)
- Open PowerShell as administrator and run: wsl --set-default-version 2
- Install Kali Linux from the Microsoft Store

> Note: to upgrade an existing WSL1 kali-linux installation, type: wsl --set-version kali-linux 2

- Run Kali and finish the initial setup

## Install Win-KeX

Install win-kex via:

```shell
kali@kali:~$ sudo apt update
kali@kali:~$
kali@kali:~$ sudo apt install -y kali-win-kex
```

## Run Win-KeX

### Win-KeX supports three modes

Window Mode:

![Window Mode](https://www.kali.org/docs/wsl/win-kex/win-kex-thelot.png)

To start Win-KeX in Window mode with sound support, run

```shell
kex --win -s
```

Refer to the Win-KeX Win usage documentation for further information.

## Enhanced Session Mode

![Enhanced Session Mode](https://www.kali.org/docs/wsl/win-kex/win-kex-wt1.png)

To start Win-KeX in Enhanced Session Mode with sound support and arm workaround, run

```shell
kex --esm --ip -s
```

Refer to the Win-KeX ESM usage documentation for further information.

## Seamless mode

![Seamless mode](https://www.kali.org/docs/wsl/win-kex/win-kex-sl.png)

To start Win-KeX in Seamless mode with sound support, run

```shell
kex --sl -s
```

Refer to the Win-KeX SL usage documentation for further information.

## Optional Steps

If you have the space, why not install “Kali with the lot”?: `sudo apt install -y kali-linux-large`

![full house](https://www.kali.org/docs/wsl/win-kex/win-kex-thelot.png)

Create a [Windows Terminal](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701) Shortcut

Choose amongst these options:

*Basic Win-KeX in window mode with sound:*

```json
{
      "guid": "{55ca431a-3a87-5fb3-83cd-11ececc031d2}",
      "hidden": false,
      "name": "Win-KeX",
      "commandline": "wsl -d kali-linux kex --wtstart -s",
},
```

*Advanced Win-KeX in window mode with sound - Kali icon and start in kali home directory:*

Copy the kali-menu.png icon across to your windows picture directory and add the icon and start directory to your WT config:

```json
{
        "guid": "{55ca431a-3a87-5fb3-83cd-11ececc031d2}",
        "hidden": false,
        "icon": "file:///c:/users/<windows user>/pictures/icons/kali-menu.png",
        "name": "Win-KeX",
        "commandline": "wsl -d kali-linux kex --wtstart -s",
        "startingDirectory" : "//wsl$/kali-linux/home/<kali user>"
},
```

*Basic Win-KeX in seamless mode with sound:*

```json
{
      "guid": "{55ca431a-3a87-5fb3-83cd-11ececc031d2}",
      "hidden": false,
      "name": "Win-KeX",
      "commandline": "wsl -d kali-linux kex --sl --wtstart -s",
},
```

*Advanced Win-KeX in seamless mode with sound - Kali icon and start in kali home directory:*

Copy the kali-menu.png icon across to your windows picture directory and add the icon and start directory to your WT config:

```json
{
        "guid": "{55ca431a-3a87-5fb3-83cd-11ececc031d2}",
        "hidden": false,
        "icon": "file:///c:/users/<windows user>/pictures/icons/kali-menu.png",
        "name": "Win-KeX",
        "commandline": "wsl -d kali-linux kex --sl --wtstart -s",
        "startingDirectory" : "//wsl$/kali-linux/home/<kali user>"
},
```

*Basic Win-KeX in ESM mode with sound:*

```json
{
      "guid": "{55ca431a-3a87-5fb3-83cd-11ecedc031d2}",
      "hidden": false,
      "name": "Win-KeX",
      "commandline": "wsl -d kali-linux kex --esm --wtstart -s",
},
```

*Advanced Win-KeX in ESM mode with sound - Kali icon and start in kali home directory:*

Copy the kali-menu.png icon across to your windows picture directory and add the icon and start directory to your WT config:

```json
{
        "guid": "{55ca431a-3a87-5fb3-83cd-11ecedd031d2}",
        "hidden": false,
        "icon": "file:///c:/users/<windows user>/pictures/icons/kali-menu.png",
        "name": "Win-KeX",
        "commandline": "wsl -d kali-linux kex --esm --wtstart -s",
        "startingDirectory" : "//wsl$/kali-linux/home/<kali user>"
},
```

## Help

For more information, ask for help via:

```shell
kex --help
```

or consult the manpage via:

```shell
man kex
```
