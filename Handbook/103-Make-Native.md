# 103-Make-Native

## Purpose
The Make package contains a program for controlling the generation of executables and other non-source files of a program from the program's source files. This is the final, native installation.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Make-4.4.1 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf make-4.4.1.tar.gz
   cd make-4.4.1
   ```
2. Configure for the system:
   ```bash
   ./configure --prefix=/usr
   ```
3. Build and install:
   ```bash
   make
   make install
   ```

## Expected Outcome
The native `make` binary is installed in `/usr/bin`.

[⬅️ Previous Step](102-Libpipeline.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](104-Patch-Native.md)

Built with ❤️ for ScratchOS.
