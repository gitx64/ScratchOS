# 104-Patch-Native

## Purpose
The Patch package contains a program for modifying or creating files by applying a "patch" file. This is the final, native installation.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Patch-2.8 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf patch-2.8.tar.xz
   cd patch-2.8
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
The native `patch` binary is installed in `/usr/bin`.

[⬅️ Previous Step](103-Make-Native.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](105-Tar-Native.md)

Built with ❤️ for ScratchOS.
