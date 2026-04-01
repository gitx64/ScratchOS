# 099-Gzip-Native

## Purpose
The Gzip package contains programs for compressing and decompressing files. This is the final, native installation of the package.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Gzip-1.14 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf gzip-1.14.tar.xz
   cd gzip-1.14
   ```
2. Configure for the system:
   ```bash
   ./configure --prefix=/usr
   ```
3. Build and install:
   ```bash
   make
   make install
   ```

## Expected Outcome
The native `gzip` binary and its related utilities are installed in `/usr/bin`.

[⬅️ Previous Step](098-Groff.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](100-IPRoute2.md)

Built with ❤️ for ScratchOS.
