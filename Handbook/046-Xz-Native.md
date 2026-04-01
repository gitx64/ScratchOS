# 046-Xz-Native

## Purpose
The Xz package contains programs for compressing and decompressing files. This is the final, native build of the package.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Xz-5.8.2 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf xz-5.8.2.tar.xz
   cd xz-5.8.2
   ```
2. Configure for the native system:
   ```bash
   ./configure --prefix=/usr                     \
               --disable-static                  \
               --docdir=/usr/share/doc/xz-5.8.2
   ```
3. Build and install:
   ```bash
   make
   make install
   ```

## Expected Outcome
The native `xz` utility and libraries are installed.

[⬅️ Previous Step](045-Bzip2.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](047-Zstd.md)

Built with ❤️ for ScratchOS.
