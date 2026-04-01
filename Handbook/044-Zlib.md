# 044-Zlib

## Purpose
The Zlib package contains compression and decompression routines used by many programs.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Zlib-1.3.2 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf zlib-1.3.2.tar.gz
   cd zlib-1.3.2
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
The Zlib library is installed in `/usr/lib`.

[⬅️ Previous Step](043-Glibc-Native.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](045-Bzip2.md)

Built with ❤️ for ScratchOS.
