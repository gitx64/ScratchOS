# 015-Linux-API-Headers

## Purpose
The Linux API Headers allow the C library (Glibc) to communicate with the kernel. These headers are essential for building the core system libraries.

## Prerequisites
- You must be logged in as the `sos` user.
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
3. Install the headers to `$SOS/usr/include`:
   ```bash
   make headers
   find usr/include -type f ! -name '*.h' -delete
   cp -rv usr/include/* $SOS/usr/include
   ```

## Expected Outcome
The Linux kernel API headers are installed in `$SOS/usr/include`.

[⬅️ Previous Step](014-GCC-Pass-1.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](016-Glibc.md)

Built with ❤️ for ScratchOS.
