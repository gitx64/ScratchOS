# 127-Linux-Kernel

## Purpose
The Linux kernel is the core of the operating system. It manages hardware resources and provides an interface for applications.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Linux-6.18.10 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf linux-6.18.10.tar.xz
   cd linux-6.18.10
   ```
2. Clean the source tree:
   ```bash
   make mrproper
   ```
3. Configure the kernel (this is a complex step; using a default configuration is recommended for beginners):
   ```bash
   make defconfig
   ```
4. Build the kernel and modules:
   ```bash
   make
   ```
5. Install the modules:
   ```bash
   make modules_install
   ```
6. Install the kernel image to `/boot`:
   ```bash
   cp -iv arch/x86/boot/bzImage /boot/vmlinuz-6.18.10-sos
   cp -iv System.map /boot/System.map-6.18.10
   cp -iv .config /boot/config-6.18.10
   ```

## Expected Outcome
The Linux kernel image and its modules are installed.

[⬅️ Previous Step](126-Fstab.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](128-GRUB-Setup.md)

Built with ❤️ for ScratchOS.
