# 021-Coreutils

## Purpose
The Coreutils package contains the basic utilities for managing files, directories, and text on our system. These include commands like `ls`, `cp`, `mv`, and `rm`.

## Prerequisites
- The cross-toolchain and Glibc must be installed.
- Sources for Coreutils-9.10 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf coreutils-9.10.tar.xz
   cd coreutils-9.10
   ```
2. Configure for cross-compilation:
   ```bash
   ./configure --prefix=/usr                     \
               --host=$SOS_TARGET                \
               --build=$(build-aux/config.guess) \
               --enable-install-program=hostname \
               --enable-no-install-program=kill,uptime
   ```
3. Build and install to `$SOS`:
   ```bash
   make
   make DESTDIR=$SOS install
   ```

## Expected Outcome
The core utilities are installed in `$SOS/usr/bin`.

[⬅️ Previous Step](020-Bash.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](022-Diffutils.md)

Built with ❤️ for ScratchOS.
