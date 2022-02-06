## linux kernel for 64bit (amd64) with latest amdgpu drivers.

Driver work checked on AMD Radeon HD 7750 (Cape Verde PRO, GCN 1.0), but will probably work on others.

Vulkan API - ok

Hardware decode video - ok

The corresponding source tree can be found here: https://gitlab.freedesktop.org/agd5f/linux/-/tree/amd-staging-drm-next

This linux kernel compiled on Linux Ubuntu 20.04, but will probably run on Debian.

To get the best Vulkan performance recommended for use with *ubuntu PPA repo https://launchpad.net/~oibaf/+archive/ubuntu/graphics-drivers

This is an **very** experimental kernel, use at your own **risk**.

Install:
1. Create a folder in a place convenient for you (for example: ~/kernel)
2. Download latest .deb packages from [release](https://github.com/Mr-Precise/linux-kernel-with-amdgpu-bin/releases): linux-libc-dev, linux-headers and linux-image
3. It is recommended to install non-free linux-firmware containing firmwares for amd video cards, etc...
4. Run `sudo dpkg -i *.deb` in this directory.
5. Reboot. Ok.  

If something goes wrong, delete them.
