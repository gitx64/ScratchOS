# 114-Util-linux

## Purpose
The Util-linux package contains many miscellaneous utility programs. Among them are utilities for handling file systems, consoles, partitions, and messages.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Util-linux-2.41.3 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf util-linux-2.41.3.tar.xz
   cd util-linux-2.41.3
   ```
2. Configure for the system:
   ```bash
   ./configure --bindir=/usr/bin    \
               --libdir=/usr/lib    \
               --runstatedir=/run   \
               --sbindir=/usr/sbin  \
               --disable-chfn-chsh  \
               --disable-login      \
               --disable-nologin    \
               --disable-su         \
               --disable-setpriv    \
               --disable-runuser    \
               --disable-pylibmount \
               --disable-static     \
               --without-python     \
               --docdir=/usr/share/doc/util-linux-2.41.3
   ```
3. Build and install:
   ```bash
   make
   make install
   ```

## Expected Outcome
The `fdisk`, `mount`, `umount`, and other critical system utilities are installed.

[⬅️ Previous Step](113-Procps.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](115-E2fsprogs.md)

Built with ❤️ for ScratchOS.
