# 022-Diffutils

## Purpose
The Diffutils package contains programs that show the differences between files or directories.

## Prerequisites
- The cross-toolchain must be installed.
- Sources for Diffutils-3.12 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf diffutils-3.12.tar.xz
   cd diffutils-3.12
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
The `diff` and `cmp` binaries are installed in `$SOS/usr/bin`.

[⬅️ Previous Step](021-Coreutils.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](023-File.md)

Built with ❤️ for ScratchOS.
