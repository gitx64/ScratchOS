# 050-M4-Native

## Purpose
The M4 package contains a macro processor. This is the final, native installation of the package.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for M4-1.4.21 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf m4-1.4.21.tar.xz
   cd m4-1.4.21
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
The native `m4` binary is installed in `/usr/bin`.

[⬅️ Previous Step](049-Readline.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](051-Bc.md)

Built with ❤️ for ScratchOS.
