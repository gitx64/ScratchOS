# 083-Automake

## Purpose
The Automake package contains programs for generating `Makefile.in` files for use with Autoconf.

## Prerequisites
- Autoconf must be installed.
- Sources for Automake-1.18.1 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf automake-1.18.1.tar.xz
   cd automake-1.18.1
   ```
2. Configure for the system:
   ```bash
   ./configure --prefix=/usr --docdir=/usr/share/doc/automake-1.18.1
   ```
3. Build and install:
   ```bash
   make
   make install
   ```

## Expected Outcome
The `automake` binary and its related scripts are installed in `/usr/bin`.

[⬅️ Previous Step](082-Autoconf.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](084-OpenSSL.md)

Built with ❤️ for ScratchOS.
