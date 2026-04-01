# 105-Tar-Native

## Purpose
The Tar package provides the ability to create archives and manipulate existing archives. This is the final, native installation.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Tar-1.35 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf tar-1.35.tar.xz
   cd tar-1.35
   ```
2. Configure for the system:
   ```bash
   FORCE_UNSAFE_CONFIGURE=1  \
   ./configure --prefix=/usr
   ```
3. Build and install:
   ```bash
   make
   make install
   make -C doc install-html docdir=/usr/share/doc/tar-1.35
   ```

## Expected Outcome
The native `tar` binary and documentation are installed.

[⬅️ Previous Step](104-Patch-Native.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](106-Texinfo.md)

Built with ❤️ for ScratchOS.
