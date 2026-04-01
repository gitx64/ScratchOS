# 098-Groff

## Purpose
The Groff package contains programs for processing and formatting text.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Groff-1.23.0 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf groff-1.23.0.tar.gz
   cd groff-1.23.0
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
The `groff` utilities and their related macro sets are installed.

[⬅️ Previous Step](097-Findutils-Native.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](099-Gzip-Native.md)

Built with ❤️ for ScratchOS.
