# 093-Coreutils-Native

## Purpose
The Coreutils package contains the basic utilities for managing files, directories, and text on our system. This is the final, native installation.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Coreutils-9.10 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf coreutils-9.10.tar.xz
   cd coreutils-9.10
   ```
2. Apply patches if needed:
   ```bash
   patch -Np1 -i ../coreutils-9.10-i18n-1.patch
   ```
3. Configure for the system:
   ```bash
   autoreconf -fiv
   FORCE_UNSAFE_CONFIGURE=1 ./configure \
               --prefix=/usr            \
               --enable-no-install-program=kill,uptime
   ```
4. Build and install:
   ```bash
   make
   make install
   ```
5. Move the binaries to their proper locations:
   ```bash
   mv -v /usr/bin/chroot /usr/sbin
   mv -v /usr/share/man/man1/chroot.1 /usr/share/man/man8/chroot.8
   sed -i 's/"1"/"8"/' /usr/share/man/man8/chroot.8
   ```

## Expected Outcome
The final native core utilities are installed in `/usr/bin` and `/usr/sbin`.

[⬅️ Previous Step](092-Meson.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](094-Check.md)

Built with ❤️ for ScratchOS.
