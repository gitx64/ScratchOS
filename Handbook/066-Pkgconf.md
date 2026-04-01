# 066-Pkgconf

## Purpose
The Pkgconf package provides a tool for managing compile and link flags for libraries. It is a modern replacement for `pkg-config`.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Pkgconf-2.5.1 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf pkgconf-2.5.1.tar.xz
   cd pkgconf-2.5.1
   ```
2. Configure for the system:
   ```bash
   ./configure --prefix=/usr              \
               --disable-static           \
               --docdir=/usr/share/doc/pkgconf-2.5.1
   ```
3. Build and install:
   ```bash
   make
   make install
   ln -sv pkgconf /usr/bin/pkg-config
   ln -sv pkgconf.1 /usr/share/man/man1/pkg-config.1
   ```

## Expected Outcome
The `pkgconf` and `pkg-config` utilities are installed.

[⬅️ Previous Step](065-GCC-Native.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](067-Ncurses-Native.md)

Built with ❤️ for ScratchOS.
