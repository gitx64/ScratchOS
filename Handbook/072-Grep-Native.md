# 072-Grep-Native

## Purpose
The Grep package contains programs for searching through files. This is the final, native installation of the package.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Grep-3.12 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf grep-3.12.tar.xz
   cd grep-3.12
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
The native `grep` binary is installed in `/usr/bin`.

[⬅️ Previous Step](071-Bison.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](073-Bash-Native.md)

Built with ❤️ for ScratchOS.
