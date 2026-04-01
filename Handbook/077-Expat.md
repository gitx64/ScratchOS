# 077-Expat

## Purpose
The Expat package contains a stream-oriented C library for parsing XML.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Expat-2.7.4 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf expat-2.7.4.tar.xz
   cd expat-2.7.4
   ```
2. Configure for the system:
   ```bash
   ./configure --prefix=/usr    \
               --disable-static \
               --docdir=/usr/share/doc/expat-2.7.4
   ```
3. Build and install:
   ```bash
   make
   make install
   ```

## Expected Outcome
The Expat library and documentation are installed.

[⬅️ Previous Step](076-Gperf.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](078-Inetutils.md)

Built with ❤️ for ScratchOS.
