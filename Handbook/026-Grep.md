# 026-Grep

## Purpose
The Grep package contains programs for searching through files.

## Prerequisites
- The cross-toolchain must be installed.
- Sources for Grep-3.12 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf grep-3.12.tar.xz
   cd grep-3.12
   ```
2. Configure for cross-compilation:
   ```bash
   ./configure --prefix=/usr   \
               --host=$SOS_TARGET \
               --build=$(build-aux/config.guess)
   ```
3. Build and install to `$SOS`:
   ```bash
   make
   make DESTDIR=$SOS install
   ```

## Expected Outcome
The `grep` binary is installed in `$SOS/usr/bin`.

[⬅️ Previous Step](025-Gawk.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](027-Gzip.md)

Built with ❤️ for ScratchOS.
