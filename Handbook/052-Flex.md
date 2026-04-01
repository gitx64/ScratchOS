# 052-Flex

## Purpose
The Flex package contains a utility for generating programs that recognize patterns in text.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Flex-2.6.4 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf flex-2.6.4.tar.gz
   cd flex-2.6.4
   ```
2. Configure for the system:
   ```bash
   ./configure --prefix=/usr \
               --docdir=/usr/share/doc/flex-2.6.4 \
               --disable-static
   ```
3. Build and install:
   ```bash
   make
   make install
   ```
4. Create a symlink for programs that expect `lex`:
   ```bash
   ln -sv flex /usr/bin/lex
   ```

## Expected Outcome
The `flex` binary and its related library are installed.

[⬅️ Previous Step](051-Bc.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](053-Tcl.md)

Built with ❤️ for ScratchOS.
