# 058-MPFR-Native

## Purpose
The MPFR package contains functions for arbitrary precision floating-point arithmetic.

## Prerequisites
- GMP must be installed.
- Sources for MPFR-4.2.2 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf mpfr-4.2.2.tar.xz
   cd mpfr-4.2.2
   ```
2. Configure for the system:
   ```bash
   ./configure --prefix=/usr        \
               --disable-static     \
               --enable-thread-safe \
               --docdir=/usr/share/doc/mpfr-4.2.2
   ```
3. Build and install:
   ```bash
   make
   make html
   make install
   make install-html
   ```

## Expected Outcome
The native MPFR library is installed.

[⬅️ Previous Step](057-GMP-Native.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](059-MPC-Native.md)

Built with ❤️ for ScratchOS.
