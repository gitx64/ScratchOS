# 062-Libcap

## Purpose
The Libcap package implements the user-space interfaces to the POSIX capabilities that are available in all modern Linux kernels. These allow the kernel to split the privileges of the `root` user into distinct groups.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Libcap-2.73 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf libcap-2.73.tar.xz
   cd libcap-2.73
   ```
2. Prevent static libraries from being installed:
   ```bash
   sed -i '/install -m.*STALIBNAME/d' libcap/Makefile
   ```
3. Build and install:
   ```bash
   make prefix=/usr lib=lib
   make prefix=/usr lib=lib install
   ```

## Expected Outcome
The `setcap` and `getcap` utilities and libraries are installed.

[⬅️ Previous Step](061-Acl.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](063-Libxcrypt.md)

Built with ❤️ for ScratchOS.
