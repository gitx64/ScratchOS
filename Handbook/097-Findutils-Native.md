# 097-Findutils-Native

## Purpose
The Findutils package contains programs to find files. This is the final, native installation of the package.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Findutils-4.10.0 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf findutils-4.10.0.tar.xz
   cd findutils-4.10.0
   ```
2. Configure for the system:
   ```bash
   ./configure --prefix=/usr --localstatedir=/var/lib/locate
   ```
3. Build and install:
   ```bash
   make
   make install
   ```

## Expected Outcome
The native `find` and `xargs` binaries are installed in `/usr/bin`.

[⬅️ Previous Step](096-Gawk-Native.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](098-Groff.md)

Built with ❤️ for ScratchOS.
