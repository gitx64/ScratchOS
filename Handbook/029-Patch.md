# 029-Patch

## Purpose
The Patch package contains a program for modifying or creating files by applying a "patch" file typically created by the `diff` program.

## Prerequisites
- The cross-toolchain must be installed.
- Sources for Patch-2.8 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf patch-2.8.tar.xz
   cd patch-2.8
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
The `patch` binary is installed in `$SOS/usr/bin`.

[⬅️ Previous Step](028-Make.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](030-Sed.md)

Built with ❤️ for ScratchOS.
