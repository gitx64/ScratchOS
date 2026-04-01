# 095-Diffutils-Native

## Purpose
The Diffutils package contains programs that show the differences between files or directories. This is the final, native installation.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Diffutils-3.12 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf diffutils-3.12.tar.xz
   cd diffutils-3.12
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
The native `diff` and `cmp` binaries are installed in `/usr/bin`.

[⬅️ Previous Step](094-Check.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](096-Gawk-Native.md)

Built with ❤️ for ScratchOS.
