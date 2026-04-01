# 025-Gawk

## Purpose
The Gawk package contains programs for manipulating text files.

## Prerequisites
- The cross-toolchain must be installed.
- Sources for Gawk-5.3.2 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf gawk-5.3.2.tar.xz
   cd gawk-5.3.2
   ```
2. For x86_64, avoid including unnecessary headers:
   ```bash
   sed -i 's/extras//' Makefile.in
   ```
3. Configure for cross-compilation:
   ```bash
   ./configure --prefix=/usr   \
               --host=$SOS_TARGET \
               --build=$(build-aux/config.guess)
   ```
4. Build and install to `$SOS`:
   ```bash
   make
   make DESTDIR=$SOS install
   ```

## Expected Outcome
The `gawk` binary is installed in `$SOS/usr/bin`.

[⬅️ Previous Step](024-Findutils.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](026-Grep.md)

Built with ❤️ for ScratchOS.
