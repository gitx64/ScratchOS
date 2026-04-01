# 063-Libxcrypt

## Purpose
The Libxcrypt package contains a modern library for one-way hashing of passwords.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Libxcrypt-4.4.36 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf libxcrypt-4.4.36.tar.xz
   cd libxcrypt-4.4.36
   ```
2. Configure for the system:
   ```bash
   ./configure --prefix=/usr                \
               --enable-hashes=strong,glibc \
               --enable-obsolete-api=no     \
               --disable-static             \
               --disable-werror
   ```
3. Build and install:
   ```bash
   make
   make install
   ```

## Expected Outcome
The `libcrypt` shared library is installed in `/usr/lib`.

[⬅️ Previous Step](062-Libcap.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](064-Shadow.md)

Built with ❤️ for ScratchOS.
