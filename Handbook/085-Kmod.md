# 085-Kmod

## Purpose
The Kmod package contains libraries and utilities for loading, inserting, and removing kernel modules.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Kmod-34 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf kmod-34.tar.xz
   cd kmod-34
   ```
2. Configure for the system:
   ```bash
   ./configure --prefix=/usr          \
               --sysconfdir=/etc      \
               --with-openssl         \
               --with-xz              \
               --with-zstd            \
               --with-zlib            \
               --disable-static
   ```
3. Build and install:
   ```bash
   make
   make install
   ```
4. Create symlinks for compatibility with standard module tools:
   ```bash
   for target in depmod insmod modinfo modprobe rmmod; do
     ln -sfv ../bin/kmod /usr/sbin/$target
   done
   ln -sfv kmod /usr/bin/lsmod
   ```

## Expected Outcome
The kernel module management utilities are installed.

[⬅️ Previous Step](084-OpenSSL.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](086-Libelf.md)

Built with ❤️ for ScratchOS.
