# 027-Gzip

## Purpose
The Gzip package contains programs for compressing and decompressing files.

## Prerequisites
- The cross-toolchain must be installed.
- Sources for Gzip-1.14 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf gzip-1.14.tar.xz
   cd gzip-1.14
   ```
2. Configure for cross-compilation:
   ```bash
   ./configure --prefix=/usr --host=$SOS_TARGET
   ```
3. Build and install to `$SOS`:
   ```bash
   make
   make DESTDIR=$SOS install
   ```

## Expected Outcome
The `gzip` binary and its related utilities are installed in `$SOS/usr/bin`.

[⬅️ Previous Step](026-Grep.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](028-Make.md)

Built with ❤️ for ScratchOS.
