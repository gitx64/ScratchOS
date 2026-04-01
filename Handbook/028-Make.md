# 028-Make

## Purpose
The Make package contains a program for controlling the generation of executables and other non-source files of a program from the program's source files.

## Prerequisites
- The cross-toolchain must be installed.
- Sources for Make-4.4.1 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf make-4.4.1.tar.gz
   cd make-4.4.1
   ```
2. Configure for cross-compilation:
   ```bash
   ./configure --prefix=/usr   \
               --without-guile \
               --host=$SOS_TARGET \
               --build=$(build-aux/config.guess)
   ```
3. Build and install to `$SOS`:
   ```bash
   make
   make DESTDIR=$SOS install
   ```

## Expected Outcome
The `make` binary is installed in `$SOS/usr/bin`.

[⬅️ Previous Step](027-Gzip.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](029-Patch.md)

Built with ❤️ for ScratchOS.
