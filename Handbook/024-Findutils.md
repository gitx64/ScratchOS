# 024-Findutils

## Purpose
The Findutils package contains programs to find files. These programs are provided to recursively search through a directory tree and to create, maintain, and search a database.

## Prerequisites
- The cross-toolchain must be installed.
- Sources for Findutils-4.10.0 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf findutils-4.10.0.tar.xz
   cd findutils-4.10.0
   ```
2. Configure for cross-compilation:
   ```bash
   ./configure --prefix=/usr                   \
               --localstatedir=/var/lib/locate \
               --host=$SOS_TARGET              \
               --build=$(build-aux/config.guess)
   ```
3. Build and install to `$SOS`:
   ```bash
   make
   make DESTDIR=$SOS install
   ```

## Expected Outcome
The `find` and `xargs` binaries are installed in `$SOS/usr/bin`.

[⬅️ Previous Step](023-File.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](025-Gawk.md)

Built with ❤️ for ScratchOS.
