## linux kernel for 64bit (amd64) with latest amdgpu drivers.

![GitHub all releases](https://img.shields.io/github/downloads/Mr-Precise/linux-kernel-with-amdgpu-bin/total?color=%23477CE0&label=Total%20downloads%3A&style=flat-square)  
This is "Ready For Use" linux kernel also helps to run the latest AMD GPUs with the open source amdgpu kernel driver.

### What for?
This is my attempt to get an outdated video card to work well with good results.  
Kernel work checked on:
- AMD Radeon HD 77XX (Cape Verde PRO, GCN 1.0)
- AMD Radeon R7 360 (Tobago PRO, GCN 2.0)
- APU / iGPU Vega 3 (Dali/Picasso, GCN 5.0)  
...but will probably work on others.  

This Linux kernel is compiled on Linux Ubuntu 22.04 (jammy), but will likely run on Linux Mint 21.3+ and other Ubuntu-based distributions.

### Features
Currently preferred for **AMD** platforms, also good Nvidia/Intel compatible.  
Used custom experimental config with support for different hardware.  
Includes a large count of drivers (big kernel).  
Enabled ntfs (read/write support).  
Enabled Android modules (binder).  
Enabled some security settings.  
And other useful (probably) settings.  

### What works?
- Vulkan - ok
- Steam Proton/Wine:
    - DXVK performance - ok
    - VKD3D performance - ok
- Hardware Decode video - ok
- Hardware Encode (vaapi) video - ok
- SteamVR/ALVR - ok
- Most hardware - ok

### What is it based on?
The corresponding kernel source code tree can be found here:  
https://gitlab.freedesktop.org/agd5f/linux/-/tree/amd-staging-drm-next  
and here:  
https://gitlab.freedesktop.org/agd5f/linux/-/branches/active

### Useful PPAs:
To get the best Vulkan / OpenGL performance recommended for use with *ubuntu PPA repo:

#### *ubuntu noble 24.04+:
- [kisak - SteamVR Experimental Graphics PPA](https://launchpad.net/~kisak/+archive/ubuntu/steamvr) `ppa:kisak/steamvr`  
- [kisak - kisak-mesa fresh PPA](https://launchpad.net/~kisak/+archive/ubuntu/kisak-mesa) `ppa:kisak/kisak-mesa`  
#### *ubuntu jammy 22.04+:
- [kisak - kisak-mesa stable PPA](https://launchpad.net/~kisak/+archive/ubuntu/turtle) `ppa:kisak/turtle`  

#### *ubuntu focal 20.04+:
(for kernel [6.11.0-rc6](https://github.com/Mr-Precise/linux-kernel-with-amdgpu-bin/releases/tag/v2024.8.25) and below)  
- [Ernst Sjöstrand - Mesa Unstable PPA](https://launchpad.net/~ernstp/+archive/ubuntu/mesaaco) `ppa:ernstp/mesaaco`  
- [Ernst Sjöstrand - Mesa Almost Stable](https://launchpad.net/~ernstp/+archive/ubuntu/mesarc) `ppa:ernstp/mesarc`  

### Vulkan Libs & SDK repo:
Useful repository with Vulkan Libs & SDK for *ubuntu 20.04/22.04/24.04.  
Contains latest libraries, headers, verify tools, glslang and SDK for develop apps.  
Actual add/instal instructions here (Ubuntu Packages):  
[vulkan.lunarg.com/sdk/home#linux](https://vulkan.lunarg.com/sdk/home#linux)  
Vulkan 1.3.283.0 latest for old LTS *ubuntu 20.04:  
[vulkan.lunarg.com/doc/sdk/1.3.283.0/linux/getting_started_ubuntu.html](https://vulkan.lunarg.com/doc/sdk/1.3.283.0/linux/getting_started_ubuntu.html)  


### Linux firmware images:
Install latest upstream firmwares for Linux kernel drivers to support new hardware  
https://gitlab.com/kernel-firmware/linux-firmware  
You can download the prepared .deb package here [releases/firmware](https://github.com/Mr-Precise/linux-kernel-with-amdgpu-bin/releases/tag/firmware)  
Required 1.5 gigabyte of free disk space and additional space in `/boot`.

### Warnings:
This is an **very** experimental kernel, use at your own **risk**.  
If something goes wrong, delete/downgrade them.  
Don't forget to remove old kernels, but keep at least 2 latest working ones just in case.

### How to install:
1. Create a folder in a place convenient for you (for example: `~/kernel`)
2. Download .deb only packages from [latest release](https://github.com/Mr-Precise/linux-kernel-with-amdgpu-bin/releases): linux-libc-dev, linux-headers and linux-image
3. Also recommended to install non-free  [linux-firmware](https://github.com/Mr-Precise/linux-kernel-with-amdgpu-bin#linux-firmware-images) containing firmwares for amd video cards, etc...
4. Run `sudo dpkg -i *.deb` in this directory.
5. Reboot. Ok.
