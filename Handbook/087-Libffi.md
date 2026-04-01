# 087-Libffi

## Purpose
The Libffi package provides a portable, high-level programming interface to various calling conventions. This allows a programmer to call any function specified by a call interface description at runtime.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Libffi-3.4.7 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf libffi-3.4.7.tar.gz
   cd libffi-3.4.7
   ```
2. Configure for the system:
   ```bash
   ./configure --prefix=/usr          \
               --disable-static       \
               --with-gcc-arch=native
   ```
3. Build and install:
   ```bash
   make
   make install
   ```

## Expected Outcome
The Libffi library is installed in `/usr/lib`.

[⬅️ Previous Step](086-Libelf.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](088-Python.md)

Built with ❤️ for ScratchOS.
