# 075-GDBM

## Purpose
The GDBM package contains the GNU Database Manager. This is a library of database functions that use extensible hashing and work similar to the standard UNIX dbm.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for GDBM-1.26 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf gdbm-1.26.tar.gz
   cd gdbm-1.26
   ```
2. Configure for the system:
   ```bash
   ./configure --prefix=/usr    \
               --disable-static \
               --enable-libgdbm-compat
   ```
3. Build and install:
   ```bash
   make
   make install
   ```

## Expected Outcome
The GDBM library and utilities are installed in `/usr/lib` and `/usr/bin`.

[⬅️ Previous Step](074-Libtool.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](076-Gperf.md)

Built with ❤️ for ScratchOS.
