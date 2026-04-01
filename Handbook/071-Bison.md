# 071-Bison

## Purpose
The Bison package contains a general-purpose parser generator. It is used to create parsers for many different languages.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Bison-3.8.2 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf bison-3.8.2.tar.xz
   cd bison-3.8.2
   ```
2. Configure for the system:
   ```bash
   ./configure --prefix=/usr --docdir=/usr/share/doc/bison-3.8.2
   ```
3. Build and install:
   ```bash
   make
   make install
   ```

## Expected Outcome
The `bison` binary and its related files are installed in `/usr/bin`.

[⬅️ Previous Step](070-Gettext.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](072-Grep-Native.md)

Built with ❤️ for ScratchOS.
